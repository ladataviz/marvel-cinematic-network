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
  <div class="div-block-10"  style="background-image: url('./images/startBasePhase2.png')" in:fade|local out:fade|local/>    
  {:else}
  <div class="div-block-10"  style="background-image: url('./images/basePhase2.png')" in:fade|local out:fade|local/>    
  {/if}
{/if}

{#if innerWidth>1280}
{#if scrollDynamic % 900 >= 400 && scrollDynamic % 900 <= 700 && mounted }
  <div class="div-block-10"  style="background-image: url('./images/{moviePictureId}.png')" in:fade|local out:fade|local/>    
{/if}
{:else}
  {#if scrollDynamic % 1800 >= 400 && scrollDynamic % 1800 <= 1000 && mounted }
  <div class="div-block-10"  style="background-image: url('./images/{moviePictureId}.png')" in:fade|local out:fade|local/>    
{/if} 
{/if}
