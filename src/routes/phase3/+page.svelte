<script>
    import * as d3 from 'd3';
    import data from '$lib/phase3.js';
    import MainSection from '$lib/MainSection.svelte'
    import {size} from "$lib/ColorHandler.svelte"
 

    let phase = 3
   let csv = './phase3.csv'


  let links = data.links.map(d => Object.create(d));
  let nodes = data.nodes.map(d => Object.create(d));  

  // **** Scale for bubble size
  let sizeScalePers = d3
    .scaleLinear()
    .domain([1, 7])
    .range([4, 50]);

 // **** Scale for bubble size
  let sizeScaleMovie = d3
    .scaleSqrt()
    .domain([14, 66])
    .range([30, 60]);

  let sizeLinks = links;

  // **** Create Force simulation
  let simulation = d3
    .forceSimulation(nodes)
    .force("charge", d3.forceManyBody().strength(-183).theta(0))
    .force("link", d3.forceLink(links).id(d => d.id))
    .force("collide", d3.forceCollide( 
      d=> d.type == 'character' 
      ? size(d.id, d.type,sizeScalePers,sizeScaleMovie,sizeLinks)+2
        : size(d.id,d.type,sizeScalePers,sizeScaleMovie,sizeLinks)+20 ))
    .force("x", d3.forceX().strength(0.10))
    .force("y", d3.forceY().strength(0.17 ))
    .alphaTarget(0);


  </script>

  <MainSection {phase} {csv} {links} {nodes} {simulation} {sizeLinks} {sizeScaleMovie} {sizeScalePers} />

