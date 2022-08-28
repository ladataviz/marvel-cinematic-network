<script>
  import * as d3 from 'd3';
  import {size} from "$lib/Handler.svelte"
  import HeaderSection from '$lib/HeaderSection.svelte';
  import Tooltip from '$lib/Tooltip.svelte';
  import { fade } from 'svelte/transition';
  import nodes from '$lib/mainNodes.js';
  import links from '$lib/mainLinks.js';
  import { onMount } from "svelte";
  // import data from "$lib/data/all.js";

  let start = 0
  let click = 0
  let hover = 0
  let maxH=900
  let phase=0
  let moveRight = 0
  
  let nodeHighlights = nodes
  let linkHighlights =links

    // **** Scale for bubble size
  let sizeScalePers = d3
    .scaleSqrt()
    .domain([1, 11])
    .range([6, 40]);

 // **** Scale for bubble size
  let sizeScaleMovie = d3
    .scaleSqrt()
    .domain([8, 66])
    .range([25, 60]);

  let sizeLinks = links;

  onMount(
    async () => {
      start=1
      }
    )

  // let linkSimu = data.links.map(d => Object.create(d));
  // let nodeSimu = data.nodes.map(d => Object.create(d));  

  // // **** Create Force simulation
  // let simulation = d3
  //   .forceSimulation(nodeSimu)
  //   .force("charge", d3.forceManyBody().strength(-30).theta(0))
  //   .force("link", d3.forceLink(linkSimu).id(d => d.id))
  //   .force("collide", d3.forceCollide( 
  //     d=> d.type == 'character' 
  //     ? size(d.id, d.type,sizeScalePers,sizeScaleMovie,sizeLinks)+3 
  //       : size(d.id,d.type,sizeScalePers,sizeScaleMovie,sizeLinks)+20 ))
  //     .force("center",  d3.forceCenter())
  //   .alphaTarget(0);

  //   simulation.tick(300)

  //   console.log(JSON.stringify(nodeSimu, ['x','y','type','id','movieList','name','actorName','characterName']))
  // console.log(JSON.stringify(linkSimu, ['index','source','target','x','y','id']))

      
  let innerHeight, innerWidth
  let w;
  let h;
  let scrollY;


  function appearance(target, type)
  {
    return type == 'character' ? sizeLinks.filter(d => d.target.id == target).length : sizeLinks.filter(d => d.source.id == target).length;
  }

  //Add mousemove action
  let tooltipId = '';
  let tooltipSize = '';
  let x = 0 
  let y = 0
  let show=0

  function mouseEnter(node)
  {
    tooltipId = node.type == 'movie' ? node.name : node.characterName + ' by ' + node.actorName;
    tooltipSize = node.type == 'movie' ? appearance(node.id,node.type).toString() + ' MCU main characters' : 'appears in ' + appearance(node.id,node.type).toString() + ' movie(s)'
    show=1;
    if( click == 0 )
    {
      nodeHighlights = node.type == 'character' ?
          nodes.filter(d => (d.type == 'character' &&  d.id == node.id) || (d.type=='movie' && node.movieList.includes('|'+d.id+'|')))
          :  nodes.filter(d => (d.type == 'character' &&  d.movieList.includes('|'+node.id+'|')) || (d.type=='movie' && node.id == d.id))

      linkHighlights = links.filter(d=> d.target.id == node.id || d.source.id == node.id)
      hover = 1
    }
  }

  function mouseLeave()
  {
    if( click == 0 )
    {
      nodeHighlights = nodes
      linkHighlights = links
      hover=0
      show=0;
    }
  }

  let previousNode
  function clickNode(node)
  {
    if( node != previousNode)
    {
      nodeHighlights = node.type == 'character' ?
          nodes.filter(d => (d.type == 'character' &&  d.id == node.id) || (d.type=='movie' && node.movieList.includes('|'+d.id+'|')))
          :  nodes.filter(d => (d.type == 'character' &&  d.movieList.includes('|'+node.id+'|')) || (d.type=='movie' && node.id == d.id))

      linkHighlights = links.filter(d=> d.target.id == node.id || d.source.id == node.id)
      click = 1
      previousNode=node
    }
    else
    {
      nodeHighlights = nodes
      linkHighlights = links
      click=0
      hover=0
      previousNode=null
    }    
  }

  let touched = 0
  function mouseEnterTitle(phase)
  {
    if (!touched)
    {
      let movieList = phase== 1 ? ["|ironman|","|thor|", "|captainamericathefirstavenger|"  ,"|theincrediblehulk|"  ,"|marvelstheavengers|"  ,"|ironman2|"]
    : phase == 2 ? ["ironman3"  ,"|thorthedarkworld|"  ,"|avengersageofultron|"  ,"|antman|"  ,"|guardiansofthegalaxy|"  ,"|captainamericathewintersoldier|"]
    : ["|guardiansofthegalaxyvol2|","|antmanandthewasp|","|spidermanhomecoming|","|avengersendgame|","|blackpanther|","|avengersinfinitywar|","|captainmarvel|","|captainamericacivilwar|","|doctorstrange|","|spidermanfarfromhome|","|thorragnarok|"]
    click = 0
    nodeHighlights =  nodes.filter(
      d => (d.type == 'character' && movieList.some(substring=>d.movieList.includes(substring))) 
      ||    movieList.some(substring=> ('|'+d.id+'|').includes(substring)))

    }
  }

  function touch() {touched=1}
  function mouseLeaveTitle() { nodeHighlights = nodes  }

  function handleMove(e)
  {
    x=e.clientX
    y=e.clientY
  }


  </script>


  <svelte:window bind:innerHeight bind:scrollY={scrollY} bind:innerWidth/>

  <Tooltip  {x} {y} {show} {tooltipId} {tooltipSize} />

  <HeaderSection {phase}/>
  
  <div class="div-block-11">
    <a id="1" on:touchstart={touch} on:mouseenter={() => mouseEnterTitle(1)} on:mouseleave={mouseLeaveTitle} class="linkBottom" href="phase1"><h1 class="heading bottom">phase one</h1></a>
    <a id="2" on:touchstart={touch} on:mouseenter={() => mouseEnterTitle(2)} on:mouseleave={mouseLeaveTitle} class="linkBottom" href="phase2"><h1 class="heading bottom">phase two</h1></a>
    <a id="3" on:touchstart={touch} on:mouseenter={() => mouseEnterTitle(3)} on:mouseleave={mouseLeaveTitle} class="linkBottom" ><h1 class="heading bottom" style="background-color: grey ;">phase three</h1></a>
  </div>

    <div on:mousemove={handleMove} bind:clientWidth={w} bind:clientHeight={h} class="main-viz">
     
     
      {#if start==1}
  
      <div class="div-block-10 main"  style="background-image: url('./images/all.png'); background-size: auto {innerWidth >= 1350 ? 100 :  (innerWidth/1350)*100}%" />    

      <svg viewBox="{(w-1350)/2 } 0 1350 900" class="home"> 
          {#each links as link}
            <line  
            x1={link.source.x + w/2 } 
            x2={link.target.x+ w/2} 
            y1={link.source.y + h/2} 
            y2={link.target.y+ h/2} 
            stroke-width={linkHighlights.includes(link) && ( hover || click ) ? 2.5 : 1.5  } 
            stroke={ (hover || click) ? linkHighlights.includes(link) ? "black" :"#eee" : "#eee" } />
          {/each} 
          
          {#each nodes as node}
            <circle 
            cx={node.x + w/2} 
            cy={node.y + h/2} 
            r={ size(node.id, node.type,sizeScalePers, sizeScaleMovie,sizeLinks) } 
            fill={node.type == 'character' ?  nodeHighlights.includes(node) ? "black" :"#eee" : "white"}
            stroke =  { nodeHighlights.includes(node) ? "black" :"#eee"  } 
            stroke-width=   { node.type == 'character'  ? 0 : 4} 
            />
          {/each}

          {#each links as link}
            {#if hover && linkHighlights.includes(link) }
            <line  
            x1={link.source.x + w/2 } 
            x2={link.target.x+ w/2} 
            y1={link.source.y + h/2} 
            y2={link.target.y+ h/2} 
            stroke-width={ 2.5  } 
            stroke={ linkHighlights.includes(link) ? "black" :"#eee" }
            />
            {/if}
          {/each} 

          {#each nodes as node}
            {#if hover && nodeHighlights.includes(node) }
              <circle 
              cx={node.x + w/2} 
              cy={node.y + h/2} 
              r={ size(node.id, node.type,sizeScalePers, sizeScaleMovie,sizeLinks) } 
              fill={node.type == 'character' ?   "black" : "white"}
              stroke =  {  "black"  } 
              stroke-width= { node.type == 'character'  ? 0 : 4} 

              />
              {/if}        
          {/each}
         
        </svg>

        <svg class="above home" viewBox="{(w-1350)/2 } 0 1350 900">      
          {#each nodes as node}
          <circle 
          cx={node.x + w/2} 
          cy={node.y + h/2} 
          r={ size(node.id, node.type,sizeScalePers, sizeScaleMovie,sizeLinks) } 
          fill={node.type == "movie" ? "white" : "transparent"}
          opacity= {nodeHighlights.includes(node) ? 0 :  0.9}
          stroke-width=   { node.type == 'character'  ? 0 : 4} 
          on:mouseenter={() => mouseEnter(node)}
          on:click={() =>  clickNode(node)}
          on:mouseleave={mouseLeave}
          in:fade
          />
          {/each}
        </svg>
    
  
        {/if}
      
    </div>
  

  <div class="section end wf-section small">
        <p class="paragraph-3"><em>Characters and movies are copyrighted by The Walt Disney Company and the Marvel Studio.<br>All pictures come from </em>
      <a href="https://www.klipartz.com/en" class="link">https://www.klipartz.com/en </a><em class="italic-text-2"> under anonymous non-commercial use.<br>‍</em><em>If you see one of your creations and want to be credited or want it removed, please </em>
      <a href="http://www.ladataviz.com" class="link"><em>contact me</em></a><em>!</em><br><em class="italic-text-2">Data:  <a href="https://en.wikipedia.org/wiki/List_of_Marvel_Cinematic_Universe_film_actors_(The_Infinity_Saga)" class="link">List of Marvel Cinematic Universe film actors (The Infinity Saga)</a></em>
    </p>
  </div>

  
<style>
  circle {
    transition: fill 500ms ease, stroke 500ms ease, opacity 500ms ease;

  }

  line {
    transition: stroke 400ms ease;
  }
</style>