<script>
    import * as d3 from 'd3';
    import MainSection from '$lib/MainSection.svelte'
    import nodes from '$lib/phase1Nodes.js';
    import links from '$lib/phase1Links.js';
    
    let phase = 1
    let csv = './phase1.csv'
    
    // **** Scale for bubble size
    let sizeScalePers = d3
      .scaleLinear()
      .domain([1, 5])
      .range([5, 50]);
  
   // **** Scale for bubble size
    let sizeScaleMovie = d3
      .scaleLinear()
      .domain([5, 25])
      .range([10, 70]);
  

    // let links = data.links.map(d => Object.create(d));
    // let nodes = data.nodes.map(d => Object.create(d));  
  
    // // **** Create Force simulation
    // let simulation = d3
    //   .forceSimulation(nodes)
    //   .force("charge", d3.forceManyBody().strength(-400).theta(-0.8))
    //   .force("link", d3.forceLink(links).id(d => d.id))
    //   .force("collide", d3.forceCollide(
    //        d=> d.type == 'character' 
    //        ? size(d.id, d.type, sizeScalePers, sizeScaleMovie,links)+5 
    //        : size(d.id,d.type,sizeScalePers, sizeScaleMovie,links)+40 ))
    //   .force("x", d3.forceX().strength(0.10))
    //   .force("y", d3.forceY().strength(0.30))
    //   .alphaTarget(0);
  
  
    // simulation.tick(300)

    //   console.log(JSON.stringify(nodes, ['x','y','type','id','movieList','name','actorName','characterName']))
    //   console.log(JSON.stringify(links, ['index','source','target','x','y','id']))

    </script>
  

    <MainSection {phase} {csv} {links} {nodes} {sizeScaleMovie} {sizeScalePers} />
  
  