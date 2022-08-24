<script>
    import * as d3 from 'd3';
    import data from '$lib/phase2.js';
    import MainSection from '$lib/MainSection.svelte'
    import {size} from "$lib/ColorHandler.svelte"
  
    let phase = 2
    let csv = './phase2.csv'

  let links = data.links.map(d => Object.create(d));
  let nodes = data.nodes.map(d => Object.create(d));  

  
  // **** Scale for bubble size
  let sizeScalePers = d3
    .scaleLinear()
    .domain([1, 4])
    .range([5, 40]);

 // **** Scale for bubble size
  let sizeScaleMovie = d3
    .scaleLinear()
    .domain([18, 33])
    .range([30, 60]);

  let sizeLinks = links;

  // **** Create Force simulation
  let simulation = d3
    .forceSimulation(nodes)
    .force("charge", d3.forceManyBody().strength(-250).theta(-0))
    .force("link", d3.forceLink(links).id(d => d.id))
    .force("collide", d3.forceCollide( 
      d=> d.type == 'character' 
        ? size(d.id, d.type,sizeScalePers,sizeScaleMovie,sizeLinks)+5 
        : size(d.id,d.type,sizeScalePers,sizeScaleMovie,sizeLinks)+30 ))
    .force("x", d3.forceX().strength(0.10))
    .force("y", d3.forceY().strength(0.15))
    .alphaTarget(0);


  </script>

  <MainSection {phase} {csv} {links} {nodes} {simulation} {sizeLinks} {sizeScaleMovie} {sizeScalePers} />
