<script context="module">
  
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
      }
      else{
        show=0;
      }
    };
  
    function onMouseEnter(datum) {
      tooltipId = datum.type == 'movie' ? datum.name : datum.characterName + ' by ' + datum.actorName;
      tooltipSize = datum.type == 'movie' ? appearance(datum.id,datum.type).toString() + ' MCU main characters' : 'appears in ' + appearance(datum.id,datum.type).toString() + ' movie(s)'
      x = datum.x ;
      y = datum.y;
      show=1;
    }
  </script>



