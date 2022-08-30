<script>
    import * as d3 from 'd3';
    import { onMount } from "svelte"
    import {colorCircleCharacter, colorCircleMovie, colorStrokeLine, colorStrokeMovie, colorStrokeCharacter, 
      sizeStrokeLine, size, tooltipHandler} from "./Handler.svelte"
    import PhaseSection from "./PhaseSection.svelte";
    import MovieSection from './MovieSection.svelte';
    import HeaderSection from './HeaderSection.svelte';
    import PictureHandler from './PictureHandler.svelte';
    import Tooltip from './Tooltip.svelte';
    import FooterSection from './FooterSection.svelte';

    export let phase;
    export let csv;
    export let nodes;
    export let links;
    export let sizeScaleMovie
    export let sizeScalePers

    let sizeLinks = links
    let nodeHighlights = nodes
    let linkHighlights =links

    let movieData = []
    let movieList = []
    let moviePictureId;

    let movie;
    let mounted;
    let maxH;
    let innerHeight, innerWidth
    let w;
    let h;
    let sizeHeader

    let moveRight = phase==3 ? -70 : phase==2 ? -50 : 0

    let scrollY;
    let percentScroll=0;
    let scrollDynamic;

    let tooltipId = '';
    let tooltipSize = '';
    let x = 0 
    let y = 0

    let hover=0
    let click=0
    let start=1;
    let show=0
    
  
    onMount(
      async () => {
        movieData = await d3.csv(csv)
        movieList = movie == 0 ? movieData.map(d=> d.movieId) : movieData.map(d=> parseInt(d.sort) <= movie ? d.movieId :'' )
        sizeLinks = links.filter(item => movieList.includes(item.source.id));
        moviePictureId = 'phase'+phase
        mounted=1  
        sizeHeader = innerWidth <= 1280 ? 500 : innerWidth < 500 ? 550 : 450
        scroll() 
      }
    )

      //	filter function
    function scroll() 
    {
      let oldMovie = movie
  
      maxH = 900


      scrollDynamic = scrollY + (innerHeight-maxH)/2 - sizeHeader
      percentScroll = Math.round((scrollDynamic)/(Math.max(h,maxH)))
  
      start = percentScroll >= 1 ? 0 : start

      movie = start==1 || percentScroll == 0  ? 0 : percentScroll

      if ( movie >=0 && movie<=movieData.length) {moviePictureId = movie == 0 || mounted==0  ? "phase"+phase : movieData[movie-1].movieId }
  
      if(percentScroll >0)
      {
        nodeHighlights = nodes
        linkHighlights = links
        click=0
        hover=0
        previousClickedNode=null
      }
      
      if(oldMovie!=movie)
      {
        movieList = movie <= 0 ? movieData.map(d=> d.movieId) : movieData.map(d=> parseInt(d.sort) <= movie ? d.movieId :'' )
    
        sizeLinks = links.filter(item => movieList.includes(item.source.id));
      }
    }

    function highlightNodes(node)
    {
      return node.type == 'character' ?
            nodes.filter(d => (d.type == 'character' &&  d.id == node.id) || ((d.type=='movie' || d.type=='phase') && node.movieList.includes('|'+d.id+'|')))
            :  nodes.filter(d => (d.type == 'character' &&  d.movieList.includes('|'+node.id+'|')) || ( (d.type=='movie' || d.type=='phase') && node.id == d.id))
    }

    function highlightLinks(node) { return links.filter(d=> d.target.id == node.id || d.source.id == node.id) }

    function mouseEnter(node)
    {
      let toolipValues = tooltipHandler(node,sizeLinks)

      tooltipId=toolipValues.tooltipId
      tooltipSize=toolipValues.tooltipSize
      show=1;

      if(!click)
      {
        nodeHighlights = highlightNodes(node)
        linkHighlights = highlightLinks(node) 
        hover = 1
      }
    }

  function mouseLeave()
  {
    if(click == 0)
    {
      nodeHighlights = nodes
      linkHighlights = links
      hover=0
    }
    show=0;
  }

  let previousClickedNode
  function clickNode(node)
  {
    if(percentScroll <= 0)
      {
        if( node != previousClickedNode)
        {
          nodeHighlights = highlightNodes(node)
          linkHighlights = highlightLinks(node) 
          click = 1
          previousClickedNode=node
        }
        else
        {
          nodeHighlights = nodes
          linkHighlights = links
          hover=0
          click=0
          previousClickedNode=null
        }    
     }
  }

  function handleMove(e)
  {
    x=e.clientX
    y=e.clientY
  }

  </script>  



  <svelte:window on:mousemove={handleMove} bind:innerHeight on:scroll={scroll} bind:scrollY={scrollY} bind:innerWidth/>
  
  <Tooltip {x} {y} {show} {tooltipId} {tooltipSize} />
  
  <HeaderSection {phase}/>
  
  <div class="section-main wf-section phase{phase}" >
   
    <div bind:clientWidth={w} bind:clientHeight={h} class="div-block-2" style:position="sticky" style:top={ (innerHeight-900)/2}px>
  
      <PictureHandler {innerWidth} {scrollDynamic} {moviePictureId} {mounted} {phase} {sizeHeader} {movie}/>
      
      {#if movieList.length>0}
        <svg viewBox="{(w-900)/2 } 0 900 900"> 
          {#each links as link}
            <line 
            class={  movieList.includes(link.source.id) ? 'in' : 'out' } 
            x1={link.source.x + w/2 + moveRight} 
            x2={link.target.x+ w/2+ moveRight} 
            y1={link.source.y + h/2} 
            y2={link.target.y+ h/2} 
            stroke-width={ percentScroll > 0 ?  movieList.includes(link.source.id) ? sizeStrokeLine(link.source.id, percentScroll,phase) : 0
              : linkHighlights.includes(link) && ( hover || click ) ? 2.5 : 1} 
            stroke={ percentScroll > 0 ? colorStrokeLine(link.source.id, percentScroll,phase) 
              :(hover || click) ? linkHighlights.includes(link) ? "black" :"#eee" : phase ==3 ? "#ccc" : phase==2 ? "#777" : "black" }/>
          {/each} 
        
          {#each nodes as node}
            <circle 
            class={'in' } 
            id={node.id}
            cx={node.x + w/2+ moveRight} 
            cy={node.y + h/2} 
            r={ size(node.id, node.type,sizeScalePers, sizeScaleMovie,sizeLinks) } 
            fill={ percentScroll > 0 ? node.type == 'character' ? colorCircleCharacter(node,percentScroll,phase) : colorCircleMovie(node.id,percentScroll)
                : node.type == 'character' ?  nodeHighlights.includes(node) ? "black" :"#eee" : "white" }
            stroke ={ percentScroll > 0 ? node.type == 'character' ? colorStrokeCharacter(node.id) : colorStrokeMovie(node.id,percentScroll,phase)
              : nodeHighlights.includes(node) ? "black" :"#eee"} 
            stroke-width= { node.type == 'character'  ? 0 : 4} 
            />
           {/each}

          {#if percentScroll <=0 && hover}
            {#each linkHighlights as link}
              <line  
              class="start"
              x1={link.source.x + w/2+ moveRight } 
              x2={link.target.x+ w/2+ moveRight} 
              y1={link.source.y + h/2} 
              y2={link.target.y+ h/2} 
              stroke-width={ 2.5} 
              stroke={ linkHighlights.includes(link) ? "black" :"#eee" }
              />
            {/each} 

            {#each nodeHighlights as node}
              <circle 
              class="start"
              cx={node.x + w/2+ moveRight} 
              cy={node.y + h/2} 
              r={ size(node.id, node.type,sizeScalePers, sizeScaleMovie,sizeLinks)  } 
              fill={node.type == 'character' ?   "black" : "white"}
              stroke =  {  "black"  } 
              stroke-width= { node.type == 'character'  ? 0 : 4} 
              />
            {/each}
          {/if}
        </svg>

        <svg class="above" viewBox="{(w-900)/2 } 0 900 900">       
          {#each nodes as node}
            <circle 
            class="start"
            cx={node.x + w/2+ moveRight} 
            cy={node.y + h/2} 
            r={ size(node.id, node.type,sizeScalePers, sizeScaleMovie,sizeLinks) + (node.type=='phase' || node.id=='joshbrolinthanos'  ? 3 :2) } 
            fill={ percentScroll <=0 ? node.type == "movie" || node.type == "phase" || node.id=='joshbrolinthanos'  ? "white" : "transparent" : "transparent"}
            opacity= {nodeHighlights.includes(node) ? 0 :  0.9}
            stroke-width=   { node.type == 'character'  ? 0 : 4} 
            on:mouseenter={() => mouseEnter(node)}
            on:click={() =>  clickNode(node)}
            on:mouseleave={mouseLeave}
            />
          {/each}
        </svg>
      {/if}

    </div>
  </div>
  
  <PhaseSection {phase} />
  
  {#each movieData as movie}
   {#if movie.phase==0}
      <MovieSection 
        name={movie.movie}
        sort={movie.sort}
        score={movie.score}
        boxOffice={movie.boxOffice}
        release={movie.release}
        phase={phase}
        />
    {/if}
  {/each}

    
  <FooterSection {phase} />


<style>
  circle.start {
    transition: fill 500ms ease, stroke 500ms ease, opacity 500ms ease;
  }  
</style>

