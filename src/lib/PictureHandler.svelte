<script>
  import { fade } from 'svelte/transition';

export let scrollDynamic
export let mounted
export let moviePictureId
export let innerWidth
export let phase

</script>

{#if phase==2 }
  {#if scrollDynamic<500}
  <div class="div-block-10"  style="background-image: url('./images/startBasePhase2.png'); background-size: auto {innerWidth >= 1280 ? 100 : innerWidth >= 600 ?61.05  : (innerWidth/900)*100}%" in:fade|local out:fade|local/>    
  {:else}
  <div class="div-block-10"  style="background-image: url('./images/basePhase2.png'); background-size: auto {innerWidth >= 1280 ? 100 : innerWidth >= 500 ?61.05  : (innerWidth/900)*100}%" in:fade|local out:fade|local/>    
  {/if}
{/if}

  {#if scrollDynamic % 900 >= 0 && scrollDynamic % 900 <= 400 && mounted || scrollDynamic<300 }
    <div class="div-block-10"  style="background-image: url('./images/{moviePictureId}.png'); background-size: auto {innerWidth >= 1280 ? 100 : innerWidth >= 550 ? 61.05  :  (innerWidth/900)*100}%" in:fade|local out:fade|local/>    
  {/if}
