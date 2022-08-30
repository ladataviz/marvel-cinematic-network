<script>
  import { fade } from 'svelte/transition';

export let scrollDynamic
export let mounted
export let moviePictureId
export let innerWidth
export let phase
export let movie
export let sizeHeader

$: scroll = scrollDynamic-sizeHeader

</script>

{#if phase==2 || phase == 3 && movie != 11 && movie != 12 }
  {#if scrollDynamic<500}
  <div class="div-block-10"  style="background-image: url('./images/startBasePhase{phase}.png'); background-size: auto {innerWidth >= 1280 ? 100 : innerWidth >= 600 ?61.05  : (innerWidth/900)*100}%" in:fade|local out:fade|local/>    
  {:else}
  <div class="div-block-10"  style="background-image: url('./images/basePhase{phase}.png'); background-size: auto {innerWidth >= 1280 ? 100 : innerWidth >= 500 ?61.05  : (innerWidth/900)*100}%" in:fade|local out:fade|local/>    
  {/if}
{/if}


{#key {movie}}
  {#if scroll % 900 >= (movie == 8 || movie ==12 ? 10 : 200) && scroll % 900 <=  (movie == 7 || movie ==11 || movie ==12  ? 890 : 700) && mounted || scrollDynamic<300 }
    <div class="div-block-10">
      <img class="imgMovie" src='./images/{moviePictureId}.png' alt="Picture of {moviePictureId}" style="height: {innerWidth >= 1280 ? 100 : innerWidth >= 550 ? 61.05  :  (innerWidth/900)*100}%;" transition:fade|local/>
    </div>
  {/if}
{/key}
