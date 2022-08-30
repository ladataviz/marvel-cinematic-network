<script>

let preloadImageUrls=['/images/ironman3.png',
 '/images/thorthedarkworld.png',
 '/images/captainamericathewintersoldier.png',
 '/images/guardiansofthegalaxy.png',
 '/images/avengersageofultron.png',
 '/images/antman.png',
 '/images/phase2.png']
</script>
    
<svelte:head>
    {#each preloadImageUrls as image}
      <link rel="preload" as="image" href={image} />
    {/each}
</svelte:head>

<slot></slot>