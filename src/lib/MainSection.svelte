<script>
    import * as d3 from 'd3';
    import { onMount } from "svelte"
    import {colorCircleCharacter, colorStrokeLine, colorStrokeMovie, colorCircleMovie, colorStrokeCharacter, sizeStrokeLine, size} from "./ColorHandler.svelte"
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
    export let simulation;   
    export let sizeLinks;
    export let sizeScaleMovie
    export let sizeScalePers

    let movieData = []
    let movieList = []
    let movie=0;
    let mounted = 0;
    let preloadImageUrls =[]
    let maxH=900
    let moveRight = phase==3 ? -70 : phase==2 ? -50 : 0

    onMount(
      async () => {
          movieData = await d3.csv(csv)
      movieList = movie == 0 ? movieData.map(d=> d.movieId) : movieData.map(d=> parseInt(d.sort) <= movie ? d.movieId :'' )
      sizeLinks = links.filter(item => movieList.includes(item.source.id));
      moviePictureId = 'phase'+phase
      mounted=1  
      if (innerWidth<1280) {maxH=1800} 
      preloadImageUrls = movieData.map( d => { if (d.score != '0') { return `/images/${d.movieId}.png` } } );
      preloadImageUrls.push('/images/phase'+phase+'.png')
      scroll() 
      }
    )
  
    let start=1;
    
    let percentScroll=0;
    let scrollDynamic;
    let moviePictureId;
  
    let innerHeight, innerWidth
    let w;
    let h;
    let scrollY;
    
  
    simulation.tick(400)
    simulation.on("tick", ticked);
  
    function ticked() {
      nodes = nodes;
      links = links;
    };
  
      //	filter function
    function scroll() 
    {
      let oldMovie = movie
  
      maxH = innerWidth<1280 ? 1800 : 900
  
      scrollDynamic = scrollY + (innerHeight-maxH)/2
      percentScroll = Math.round((scrollDynamic-500)/(Math.max(h,maxH)))
  
      start = percentScroll >= 1 ? 0 : start
      movie = start==1 || percentScroll == 0  ? 0 : percentScroll
      moviePictureId = movie == 0 || mounted==0  ? "phase"+phase : movieData[movie-1].movieId
  
      if(oldMovie!=movie)
      {
        movieList = movie == 0 ? movieData.map(d=> d.movieId) : movieData.map(d=> parseInt(d.sort) <= movie ? d.movieId :'' )
        sizeLinks = links.filter(item => movieList.includes(item.source.id));
        ticked()
      }
    }
  
    function appearanceMovie(target)
    {
      return  sizeLinks.filter(d => d.source.id == target).length  + ' MCU main characters' ;
    }

    function appearanceCharacter(target)
    {
            return 'appears in ' + sizeLinks.filter(d => d.target.id == target && d.source.score != 0).length + ' movie(s)';
    }

    function appearancePhase(target)
    {
      let nb = sizeLinks.filter(d => d.target.id == target && d.source.score == 0).length

      return nb == 0 ? '' : ' and ' + nb  + ' previous phase(s)';
    }
  
    //Add mousemove action
    let closeNode;
    let tooltipId = '';
    let tooltipSize = '';
    let x = 0 
    let y = 0
    let show=0

    function mouseMove(e) {
      const p = d3.pointer(e);
      closeNode = simulation.find(p[0]-w/2 - moveRight, p[1]-maxH/2, 20);
      if(closeNode)
      {
        size(closeNode.id,closeNode.type, sizeScalePers, sizeScaleMovie,sizeLinks)!=0 ? onMouseEnter(closeNode) : show=0;
        highlight(closeNode.id, closeNode.type)
      }
      else{
        show=0;
      }
    };
  
    function onMouseEnter(datum) {
      tooltipId = datum.type != 'character' ? datum.name : datum.characterName + ' by ' + datum.actorName;
      tooltipSize = datum.type != 'character' ? appearanceMovie(datum.id).toString()
                  :  appearanceCharacter(datum.id).toString() + appearancePhase(datum.id).toString()
      x = datum.x ;
      y = datum.y;
      show=1;
    }
  </script>
  
  <svelte:head>
      {#each preloadImageUrls as image}
        <link rel="preload" as="image" href={image} />
      {/each}
  </svelte:head>
  
  <svelte:window bind:innerHeight on:scroll={scroll} bind:scrollY={scrollY} bind:innerWidth/>

  <HeaderSection {phase}/>
  
  <div class="section-main wf-section phase{phase}" >
   
    <div on:mousemove={mouseMove} bind:clientWidth={w} bind:clientHeight={h} class="div-block-2" style:position="sticky" style:top={ (innerHeight-900)/2}px>
  
      <PictureHandler {innerWidth} {scrollDynamic} {moviePictureId} {mounted} {phase}/>

      <svg> 
        {#if movieList.length>0}
          {#each links as link}
            <line 
            class={ movieList.includes(link.source.id) ? 'in' : 'out  ' } 
            x1={link.source.x + w/2 + moveRight} 
            x2={link.target.x+ w/2+ moveRight} 
            y1={link.source.y + h/2} 
            y2={link.target.y+ h/2} 
            stroke-width={ movieList.includes(link.source.id) ? sizeStrokeLine(link.source.id, percentScroll,phase) : 0 } 
            stroke={colorStrokeLine(link.source.id, percentScroll,phase)}/>
          {/each} 
          
          {#each nodes as node}
            <circle 
            class={ start ==0 ? 'in' : 'out  ' } 
            id={node.id}
            cx={node.x + w/2+ moveRight} 
            cy={node.y + h/2} 
            r={ size(node.id, node.type,sizeScalePers, sizeScaleMovie,sizeLinks) } 
            fill={node.type == 'character' ? colorCircleCharacter(node,percentScroll,phase) : nodes.type == "movie" ? colorCircleMovie(node.id) : "white"}
            stroke =  { node.type == 'character' ? colorStrokeCharacter(node.id) : colorStrokeMovie(node.id,percentScroll,phase)} 
            stroke-width=   { node.type == 'character'  ? 0 : 3} 
            stroke-dasharray=  { node.type == 'phase'  ? 0 : 0}  />
          {/each}
        
        {/if}
      </svg>
  
      <Tooltip {moveRight} {x} {y} {w} {maxH} {show} {tooltipId} {tooltipSize} />
      
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