<script>

let preloadImageUrls=['/images/captainamericacivilwar.png',
 '/images/doctorstrange.png',
 '/images/guardiansofthegalaxyvol2.png',
 '/images/spidermanhomecoming.png',
 '/images/thorragnarok.png',
 '/images/blackpanther.png',
 '/images/avengersinfinitywar.png',
 '/images/avengersinfinitywar2.png',
 '/images/antmanandthewasp.png',
 '/images/captainmarvel.png',
 '/images/avengersendgame.png',
 '/images/avengersendgame2.png',
 '/images/spidermanfarfromhome.png',
 '/images/phase3.png']
</script>
    
<svelte:head>
    {#each preloadImageUrls as image}
      <link rel="preload" as="image" href={image} />
    {/each}
</svelte:head>

<slot></slot>