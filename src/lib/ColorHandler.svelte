<script context="module">
  let colorIronMan = "#aa0406"
  let colorHulk = "#0b8c28"
  let colorCaptain = "#1849CA"
  let colorThor = "#F7BE00"
  let colorMarvel = 'red'
  let colorGuardians = "#6E3AFF"
  let colorBoring12 = "#ddd"
  let colorBoring3 = "#eee"
  let colorAntman = 'orange'
  let colorSpider = "#DF1F2C"
  let colorCaptainMarvel = "#047CB6"

export function colorCircleCharacter(node, percentScroll, phase)
{
  let color = percentScroll%2== 0 ? colorBoring3 : colorBoring12
  if (percentScroll==0 || scrollY==0) {color="black"}

  if (phase==1)
  {
    if (percentScroll==1 && node.movieList.includes('|ironman|')) {color= colorIronMan}
    if (percentScroll==2 && node.movieList.includes('|theincrediblehulk|')) {color= colorHulk}
    if (percentScroll==3 && node.movieList.includes('|ironman2|')) {color= colorIronMan}
    if (percentScroll==5 && node.movieList.includes('|captainamericathefirstavenger|')) {color= colorCaptain}
    if (percentScroll==4 && node.movieList.includes('|thor|')) {color= colorThor}
    if (percentScroll==6 && node.movieList.includes('|marvelstheavengers|')) {color= colorMarvel}
  }
  else if (phase == 2 )
  {
    if (percentScroll==1 && node.movieList.includes('|ironman3|')) {color= colorIronMan}
    if (percentScroll==2 && node.movieList.includes('|thorthedarkworld|')) {color= colorThor}
    if (percentScroll==3 && node.movieList.includes('|captainamericathewintersoldier|')) {color= colorCaptain}
    if (percentScroll==4 && node.movieList.includes('|guardiansofthegalaxy|')) {color= colorGuardians}
    if (percentScroll==5 && node.movieList.includes('|avengersageofultron|')) {color= colorMarvel}
    if (percentScroll==6 && node.movieList.includes('|antman|')) {color= colorAntman}
  }
  else if (phase == 3 )
  {
    if (percentScroll==1 && node.movieList.includes('|captainamericacivilwar|')) {color= colorCaptain}
    if (percentScroll==2 && node.movieList.includes('|doctorstrange|')) {color= colorHulk}
    if (percentScroll==3 && node.movieList.includes('|guardiansofthegalaxyvol2|')) {color= colorGuardians}
    if (percentScroll==4 && node.movieList.includes('|spidermanhomecoming|')) {color= colorSpider}
    if (percentScroll==5 && node.movieList.includes('|thorragnarok|')) {color= colorThor}
    if (percentScroll==6 && node.movieList.includes('|blackpanther|')) {color= "black"}
    if (percentScroll==7 && node.movieList.includes('|avengersinfinitywar|')) {color= colorMarvel}
    if (percentScroll==8 && node.movieList.includes('|antmanandthewasp|')) {color= colorAntman}
    if (percentScroll==9 && node.movieList.includes('|captainmarvel|')) {color= colorCaptainMarvel}
    if (percentScroll==10 && node.movieList.includes('|avengersendgame|')) {color= colorMarvel}
    if (percentScroll==12 && node.movieList.includes('|spidermanfarfromhome|')) {color= colorSpider}
  }
  
  return color 
}

export  function colorCircleMovie(id)
{
  let color = "#aa0406"

if (id=='ironman') {color= colorIronMan}
if (id=='theincrediblehulk') {color= colorHulk}
if (id=='ironman2') {color= colorIronMan}
if (id=='captainamericathefirstavenger') {color= colorCaptain}
if (id=='thor') {color= colorThor}
if (id=='marvelstheavengers') {color= colorMarvel}
  if (id=='ironman3') {color= colorIronMan}
  if (id=='thorthedarkworld') {color= colorThor}
  if (id=='captainamericathewintersoldier') {color= colorCaptain}
  if (id=='guardiansofthegalaxy') {color= colorGuardians}
  if (id=='avengersageofultron') {color= colorMarvel}
  if (id=='antman') {color= colorAntman}
if (id=='captainamericacivilwar') {color= colorCaptain}
  if (id=='doctorstrange') {color= colorHulk}
  if (id=='guardiansofthegalaxyvol2') {color= colorGuardians}
  if (id=='spidermanhomecoming') {color= colorSpider}
  if (id=='thorragnarok') {color= colorThor}
  if (id=='blackpanther') {color= "black"}
  if (id=='avengersinfinitywar') {color= colorMarvel}
  if (id=='antmanandthewasp') {color= colorAntman}
  if (id=='captainmarvel') {color= colorCaptainMarvel}
  if ( id=='avengersendgame') {color= colorMarvel}
  if ( id=='spidermanfarfromhome') {color= colorSpider}

  return color
}

export function colorStrokeMain(id)
{
  let color = "#aa0406"

    if (id=='ironman') {color= colorIronMan}
  if (id=='theincrediblehulk') {color= colorHulk}
  if (id=='ironman2') {color= colorIronMan}
  if (id=='captainamericathefirstavenger') {color= colorCaptain}
  if (id=='thor') {color= colorThor}
  if (id=='marvelstheavengers') {color= colorMarvel}
      if (id=='ironman3') {color= colorIronMan}
      if (id=='thorthedarkworld') {color= colorThor}
      if (id=='captainamericathewintersoldier') {color= colorCaptain}
      if (id=='guardiansofthegalaxy') {color= colorGuardians}
      if (id=='avengersageofultron') {color= colorMarvel}
      if (id=='antman') {color= colorAntman}
    if (id=='captainamericacivilwar') {color= colorCaptain}
      if (id=='doctorstrange') {color= colorHulk}
      if (id=='guardiansofthegalaxyvol2') {color= colorGuardians}
      if (id=='spidermanhomecoming') {color= colorSpider}
      if (id=='thorragnarok') {color= colorThor}
      if (id=='blackpanther') {color= "black"}
      if (id=='avengersinfinitywar') {color= colorMarvel}
      if (id=='antmanandthewasp') {color= colorAntman}
      if (id=='captainmarvel') {color= colorCaptainMarvel}
      if ( id=='avengersendgame') {color= colorMarvel}
      if ( id=='spidermanfarfromhome') {color= colorSpider}

      return color
  
}


export function colorStrokeCharacter(id)
{
  let color = 'black'
 // if (percentScroll==1 && id=='ironman') {color= "#fbca03"}
  return color 
}


export function colorStrokeMovie(id, percentScroll, phase)
{
  let color = percentScroll%2== 0 ? colorBoring3 : colorBoring12
  if (percentScroll==0 || scrollY==0) {color="black"}

  if (phase==1)
  {
    if (percentScroll==1 && id=='ironman') {color= colorIronMan}
  if (percentScroll==2 && id=='theincrediblehulk') {color= colorHulk}
  if (percentScroll==3 && id=='ironman2') {color= colorIronMan}
  if (percentScroll==5 && id=='captainamericathefirstavenger') {color= colorCaptain}
  if (percentScroll==4 && id=='thor') {color= colorThor}
  if (percentScroll==6 && id=='marvelstheavengers') {color= colorMarvel}
  }
  else if (phase == 2 )
  {
      if (percentScroll==1 && id=='ironman3') {color= colorIronMan}
      if (percentScroll==2 && id=='thorthedarkworld') {color= colorThor}
      if (percentScroll==3 && id=='captainamericathewintersoldier') {color= colorCaptain}
      if (percentScroll==4 && id=='guardiansofthegalaxy') {color= colorGuardians}
      if (percentScroll==5 && id=='avengersageofultron') {color= colorMarvel}
      if (percentScroll==6 && id=='antman') {color= colorAntman}
  }
  else if (phase == 3 )
  {
    if (percentScroll==1 && id=='captainamericacivilwar') {color= colorCaptain}
      if (percentScroll==2 && id=='doctorstrange') {color= colorHulk}
      if (percentScroll==3 && id=='guardiansofthegalaxyvol2') {color= colorGuardians}
      if (percentScroll==4 && id=='spidermanhomecoming') {color= colorSpider}
      if (percentScroll==5 && id=='thorragnarok') {color= colorThor}
      if (percentScroll==6 && id=='blackpanther') {color= "black"}
      if (percentScroll==7 && id=='avengersinfinitywar') {color= colorMarvel}
      if (percentScroll==8 && id=='antmanandthewasp') {color= colorAntman}
      if (percentScroll==9 && id=='captainmarvel') {color= colorCaptainMarvel}
      if (percentScroll==10 && id=='avengersendgame') {color= colorMarvel}
      if (percentScroll==12 && id=='spidermanfarfromhome') {color= colorSpider}
  }

  

  return color
}

export function colorStrokeLine(id, percentScroll,phase)
{
  let color = percentScroll%2== 0 ? colorBoring3 : colorBoring12
  if (percentScroll==0 || scrollY==0) {color= phase == 3 ? "#999" : "black"}

  if (phase==1)
  {
      if (percentScroll==1 && id=='ironman') {color= colorIronMan}
    if (percentScroll==2 && id=='theincrediblehulk') {color= colorHulk}
    if (percentScroll==3 && id=='ironman2') {color= colorIronMan}
    if (percentScroll==5 && id=='captainamericathefirstavenger') {color= colorCaptain}
    if (percentScroll==4 && id=='thor') {color= colorThor}
    if (percentScroll==6 && id=='marvelstheavengers') {color= colorMarvel}
  }
  else if (phase == 2 )
  {
      if (percentScroll==1 && id=='ironman3') {color= colorIronMan}
      if (percentScroll==2 && id=='thorthedarkworld') {color= colorThor}
      if (percentScroll==3 && id=='captainamericathewintersoldier') {color= colorCaptain}
      if (percentScroll==4 && id=='guardiansofthegalaxy') {color= colorGuardians}
      if (percentScroll==5 && id=='avengersageofultron') {color= colorMarvel}
      if (percentScroll==6 && id=='antman') {color= colorAntman}
  }
  else if (phase == 3 )
  {
      if (percentScroll==1 && id=='captainamericacivilwar') {color= colorCaptain}
      if (percentScroll==2 && id=='doctorstrange') {color= colorHulk}
      if (percentScroll==3 && id=='guardiansofthegalaxyvol2') {color= colorGuardians}
      if (percentScroll==4 && id=='spidermanhomecoming') {color= colorSpider}
      if (percentScroll==5 && id=='thorragnarok') {color= colorThor}
      if (percentScroll==6 && id=='blackpanther') {color= "black"}
      if (percentScroll==7 && id=='avengersinfinitywar') {color= colorMarvel}
      if (percentScroll==8 && id=='antmanandthewasp') {color=colorAntman}
      if (percentScroll==9 && id=='captainmarvel') {color= colorCaptainMarvel}
      if (percentScroll==10 && id=='avengersendgame') {color= colorMarvel}
      if (percentScroll==12 && id=='spidermanfarfromhome') {color= colorSpider}
  }

  return color
}

export function sizeStrokeLine(id, percentScroll,phase)
{
  let size = 1

  if(phase==1)
  {
    if (percentScroll==0 || scrollY==0) {size=1}
    if (percentScroll==1 && id=='ironman') {size=3}
    if (percentScroll==2 && id=='theincrediblehulk') {size=3}
    if (percentScroll==3 && id=='ironman2') {size=3}
    if (percentScroll==5 && id=='captainamericathefirstavenger') {size=3}
    if (percentScroll==4 && id=='thor') {size=3}
    if (percentScroll==6 && id=='marvelstheavengers') {size=3}
  }
  else if (phase==2)
  {
    if (percentScroll==0 || scrollY==0) {size=1}
    if (percentScroll==1 && id=='ironman3') {size=3}
    if (percentScroll==2 && id=='thorthedarkworld') {size=3}
    if (percentScroll==3 && id=='captainamericathewintersoldier') {size=3}
    if (percentScroll==4 && id=='guardiansofthegalaxy') {size=3}
    if (percentScroll==5 && id=='avengersageofultron') {size=3}
    if (percentScroll==6 && id=='antman') {size= 3}
  }
  else if (phase==3)
  {
    if (percentScroll==0 || scrollY==0) {size=1}
    if (percentScroll==1 && id=='captainamericacivilwar') {size=3}
    if (percentScroll==2 && id=='doctorstrange') {size=3}
    if (percentScroll==3 && id=='guardiansofthegalaxyvol2') {size=3}
    if (percentScroll==4 && id=='spidermanhomecoming') {size=3}
    if (percentScroll==5 && id=='thorragnarok') {size=3}
    if (percentScroll==6 && id=='blackpanther') {size= 3}
    if (percentScroll==7 && id=='avengersinfinitywar') {size= 3}
    if (percentScroll==8 && id=='antmanandthewasp') {size= 3}
    if (percentScroll==9 && id=='captainmarvel') {size= 3}
    if (percentScroll==10 && id=='avengersendgame') {size= 3}
    if (percentScroll==12 && id=='spidermanfarfromhome') {size= 3}
  }
  return size
}


 export function size(target, type, sizeScalePers, sizeScaleMovie, sizeLinks)
    {
      let movieLength = sizeLinks.filter(d => d.source.id == target).length
      let charaLength = sizeLinks.filter(d => d.target.id == target).length
      let size = type == 'character' ? sizeScalePers(charaLength) : movieLength == 0 ? 0 : sizeScaleMovie(movieLength);
      return size >= 0 ? size : 0 ;
    }

 // function reset() 
  // {
  //   movie= 0
  //   links = data.links.map(d => Object.create(d));
  //   nodes = data.nodes.map(d => Object.create(d));  
  //   sizeLinks = links;

  //   simulation = d3
  //     .forceSimulation(nodes)
  //     .force("charge", d3.forceManyBody().strength(-550).theta(-0.8))
  //     .force("link", d3.forceLink(links).id(d => d.id))
  //     .force("collide", d3.forceCollide( d=> d.type == 'character' ? size(d.id, d.type)+5 : size(d.id,d.type)+40 ))
  //     .force("x", d3.forceX(width/2).strength(0.10))
  //     .force("y", d3.forceY(height/2).strength(0.30))
  //     .alphaTarget(0);

  //   simulation.alpha(1).alphaTarget(0).restart();

  //   simulation.tick(100)
  //   simulation.on("tick", ticked);
  // }


      // initialNodes = nodes;
    // csvtext = sortedNodes.map(  d => (d.index +","+d.id +","+d.name+ ","+d.size +","+d.x+","+d.y+","+d.star +"\n")  )
    // let csvContent = "data:text/csv;charset=utf-8,\nindex, id, name, size, x, y, star \n"+csvtext
    // console.log(csvContent) 
    // //console.log(links)
    // sourceCSV = sortedLinks.map(  d => (d.index +","+d.source.id+ ","+d.source.x +","+d.source.y+ ",source \n") )
    // targetCSV  = sortedLinks.map(  d => (d.index +","+d.target.id+ ","+d.target.x +","+d.target.y+ ", target \n") )
    // let csvContent2 = "data:text/csv;charset=utf-8,\nindex, id, x, y, type \n"+sourceCSV+targetCSV
    // console.log(csvContent2) 
</script>



