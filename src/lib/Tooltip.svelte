<script>

export let moveRight
export let x
export let y
export let w
export let maxH
export let show
export let tooltipId
export let tooltipSize

</script>


<div id="tooltip" class="tooltip" style="{ `transform: translate( calc( -50% + ${x+w/2 + moveRight}px), calc( -100% + ${y+maxH/2}px))`} ; opacity: {show ==1 ? 1 :0 } ">
  <div class="tooltip-range">{tooltipId}</div>
  <div>{tooltipSize}</div>
</div>


