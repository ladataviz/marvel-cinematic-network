<script context="module">
  let colorIronMan = "#aa0406"
  let colorHulk = "#0b8c28"
  let colorCaptain = "#1849CA"
  let colorThor = "#F7BE00"
  let colorMarvel = 'red'
  let colorGuardians = "#6E3AFF"
  let colorBoring12 = "#e6e6e6"
  let colorBoring3 = "#eee"
  let colorAntman = 'orange'
  let colorSpider = "#DF1F2C"
  let colorCaptainMarvel = "#047CB6"

export function colorCircleCharacter(node, percentScroll, phase)
{
  let color = (percentScroll > 11 ? percentScroll+2 : percentScroll>7 ? percentScroll+1 : percentScroll)%2== 0 ? colorBoring3 : colorBoring12
  if (percentScroll==0 || scrollY==0) {color="black"}

  if (percentScroll == 11 || percentScroll == 12) { {color="transparent"}}

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
    if (percentScroll==8 && node.movieList.includes('|avengersinfinitywar|')) {color= colorMarvel}
    if (percentScroll==9 && node.movieList.includes('|antmanandthewasp|')) {color= colorAntman}
    if (percentScroll==10 && node.movieList.includes('|captainmarvel|')) {color= colorCaptainMarvel}
    if (percentScroll==11 && node.movieList.includes('|avengersendgame|')) {color= colorMarvel}
    if (percentScroll==12 && node.movieList.includes('|avengersendgame|')) {color= colorMarvel}
    if (percentScroll==13 && node.movieList.includes('|spidermanfarfromhome|')) {color= colorSpider}
  }
  
  return color 
}

export function colorCircleMovie(id, percentScroll)
{
  let color = "white"
  if (percentScroll==11 || percentScroll==12 ) {color = id=="avengersendgame" ? 'white' : "transparent"}
  
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
  let color = (percentScroll > 11 ? percentScroll+2 : percentScroll>7 ? percentScroll+1 : percentScroll)%2== 0 ? colorBoring3 : colorBoring12

  
  if (percentScroll == 11 || percentScroll == 12) { {color="transparent"}}

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
    if (percentScroll==8 && id=='avengersinfinitywar') {color= colorMarvel}
    if (percentScroll==9 && id=='antmanandthewasp') {color= colorAntman}
    if (percentScroll==10 && id=='captainmarvel') {color= colorCaptainMarvel}
    if (percentScroll==11 && id=='avengersendgame') {color= colorMarvel}
    if (percentScroll==12 && id=='avengersendgame') {color= colorMarvel}
    if (percentScroll==13 && id=='spidermanfarfromhome') {color= colorSpider}
  }

  

  return color
}

export function colorStrokeLine(id, percentScroll,phase)
{
  let color = (percentScroll > 11 ? percentScroll+2 : percentScroll>7 ? percentScroll+1 : percentScroll)%2== 0 ? colorBoring3 : colorBoring12
  if (percentScroll==0 || scrollY==0) {color= phase == 3 ? "#999" : "black"}

  if (percentScroll == 11 || percentScroll == 12) { {color="transparent"}}


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
    if (percentScroll==8 && id=='avengersinfinitywar') {color= colorMarvel}
    if (percentScroll==9 && id=='antmanandthewasp') {color=colorAntman}
    if (percentScroll==10 && id=='captainmarvel') {color= colorCaptainMarvel}
    if (percentScroll==11 && id=='avengersendgame') {color= colorMarvel}
    if (percentScroll==12 && id=='avengersendgame') {color= colorMarvel}
    if (percentScroll==13 && id=='spidermanfarfromhome') {color= colorSpider}
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
    if (percentScroll==8 && id=='avengersinfinitywar') {size= 3}
    if (percentScroll==9 && id=='antmanandthewasp') {size= 3}
    if (percentScroll==10 && id=='captainmarvel') {size= 3}
    if (percentScroll==11 && id=='avengersendgame') {size= 3}
    if (percentScroll==12 && id=='avengersendgame') {size= 3}
    if (percentScroll==13 && id=='spidermanfarfromhome') {size= 3}
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

     function appearanceMovie(target,sizeLinks) { return  sizeLinks.filter(d => d.source.id == target).length  + ' main characters' }
     function appearanceCharacter(target,sizeLinks){ return 'appears in ' + sizeLinks.filter(d => d.target.id == target && !d.source.id.includes('phase')).length + ' movie(s)'   }
     function appearancePhase(target,sizeLinks)
    {
      let nb = sizeLinks.filter(d => d.target.id == target && d.source.id.includes('phase')).length
      return nb == 0 ? '' : ' and ' + nb  + ' previous phase(s)';
    }

    export function tooltipHandler(node, sizeLinks)
    {

      let tooltipId = node.type != 'character' ? node.name : node.characterName + ' by ' + node.actorName;
      let tooltipSize = node.type != 'character' ? appearanceMovie(node.id,sizeLinks)
                    :  appearanceCharacter(node.id,sizeLinks) + appearancePhase(node.id,sizeLinks)

      return {tooltipId,tooltipSize}
    }


</script>



