<script>
    import * as d3 from 'd3';
    // import data from '$lib/phase3.js';
    // import {size} from "$lib/ColorHandler.svelte"
    import MainSection from '$lib/MainSection.svelte'
    import nodes from '$lib/phase3Nodes.js';
    import links from '$lib/phase3Links.js';


    let phase = 3
   let csv = './phase3.csv'


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


  // let links = data.links.map(d => Object.create(d));
  // let nodes = data.nodes.map(d => Object.create(d));  

  // // **** Create Force simulation
  // let simulation = d3
  //   .forceSimulation(nodes)
  //   .force("charge", d3.forceManyBody().strength(-183).theta(0))
  //   .force("link", d3.forceLink(links).id(d => d.id))
  //   .force("collide", d3.forceCollide( 
  //     d=> d.type == 'character' 
  //     ? size(d.id, d.type,sizeScalePers,sizeScaleMovie,links)+2
  //       : size(d.id,d.type,sizeScalePers,sizeScaleMovie,links)+20 ))
  //   .force("x", d3.forceX().strength(0.10))
  //   .force("y", d3.forceY().strength(0.17 ))
  //   .alphaTarget(0);

  //      simulation.tick(400)

  //   console.log(JSON.stringify(nodes, ['x','y','type','id','movieList','name','actorName','characterName']))
  //   console.log(JSON.stringify(links, ['index','source','target','x','y','id']))


  </script>

  <MainSection {phase} {csv} {links} {nodes} {sizeScaleMovie} {sizeScalePers} />

