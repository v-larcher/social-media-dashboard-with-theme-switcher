<script>
  export let number;
  export let icon;
</script>

<style>
  .content {
    margin-top: 28px;
  }
  .inline-block {
    display: inline-block;
  }
  .number-green {
    font-size: 12px;
    font-weight: bold;
    color: hsl(163, 72%, 41%);
  }
  .number-red {
    font-size: 12px;
    font-weight: bold;
    color: hsl(356, 69%, 56%);
  }
  .icon {
    margin-bottom: 2px;
  }
</style>

<div class="content">
  <img class="inline-block icon" src="/assets/icon-{icon}.svg" alt="" />
  {#if icon === 'up'}
    <div class="inline-block number-green">{number}</div>
  {:else}
    <div class="inline-block number-red">{number}</div>
  {/if}
</div>
