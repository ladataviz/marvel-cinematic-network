<script>
let preloadImageUrls=['/images/ironman.png',
'/images/theincrediblehulk.png',
'/images/ironman2.png',
'/images/thor.png',
'/images/captainamericathefirstavenger.png',
'/images/marvelstheavengers.png',
'/images/phase1.png']
 
</script>
    
<svelte:head>
    {#each preloadImageUrls as image}
      <link rel="preload" as="image" href={image} />
    {/each}
</svelte:head>

<slot></slot>