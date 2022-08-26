<script>
  import * as d3 from 'd3';
  import MainSection from '$lib/MainSection.svelte'
  import nodes from '$lib/phase2Nodes.js';
  import links from '$lib/phase2Links.js';
  // import data from '$lib/phase2.js';
  // import {size} from "$lib/ColorHandler.svelte"

  let phase = 2
  let csv = './phase2.csv'
  
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


//   let links = data.links.map(d => Object.create(d));
//   let nodes = data.nodes.map(d => Object.create(d));  

//  // **** Create Force simulation
//  let simulation = d3
//     .forceSimulation(nodes)
//     .force("charge", d3.forceManyBody().strength(-250).theta(-0))
//     .force("link", d3.forceLink(links).id(d => d.id))
//     .force("collide", d3.forceCollide( 
//       d=> d.type == 'character' 
//         ? size(d.id, d.type,sizeScalePers,sizeScaleMovie,links)+5 
//         : size(d.id,d.type,sizeScalePers,sizeScaleMovie,links)+30 ))
//     .force("x", d3.forceX().strength(0.10))
//     .force("y", d3.forceY().strength(0.15))
//     .alphaTarget(0);


//    simulation.tick(300)

//     console.log(JSON.stringify(nodes, ['x','y','type','id','movieList','name','actorName','characterName']))
//     console.log(JSON.stringify(links, ['index','source','target','x','y','id']))

  </script>


  <MainSection {phase} {csv} {links} {nodes} {sizeScaleMovie} {sizeScalePers} />
