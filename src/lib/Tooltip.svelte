<script>

export let x
export let y
export let show
export let tooltipId
export let tooltipSize

</script>

<div class="tooltipholder">
  <div id="tooltip" class="tooltip" style="{ `transform: translate( calc( -50% + ${x}px), ${y-20}px)`} ; opacity: {show ==1 ? 1 :0 } ">
    <div class="tooltip-range">{tooltipId}</div>
    <div>{tooltipSize}</div>
  </div>
</div>


