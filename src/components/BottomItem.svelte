<script>
  import Stat from "./Stat.svelte";

  export let type;
  export let social_media_icon;
  export let social_media_number;
  export let data_icon;
  export let data_number;
</script>

<style>
  .container {
    background-color: hsl(227, 47%, 96%);
    padding: 15px 20px 15px 20px;
    border-radius: 3%;
  }
  .container:hover {
    background-color: hsl(227, 37%, 90%);
  }
  :global(body.dark-mode) .container {
    background-color: hsl(228, 28%, 20%);
  }
  .inline-block {
    display: inline-block;
  }
  .right {
    float: right;
  }
  .data {
    margin: 5px;
  }
  .social-media {
    margin: 5px;
  }
  .number {
    font-size: 30px;
    color: hsl(230, 17%, 14%);
    margin-top: 15px;
    margin-bottom: 0px;
  }
  :global(body.dark-mode) .number {
    color: white;
  }
  .type {
    font-size: 13.5px;
    font-weight: bold;
    color: hsl(228, 12%, 44%);
  }
  :global(body.dark-mode) .type {
    color: hsl(228, 34%, 66%);
  }
  img {
    margin-bottom: -4px;
  }
</style>

<div class="container">
  <div class="social-media">
    <div class="type inline-block">{type}</div>
    <img class="right" src="/assets/icon-{social_media_icon}.svg" alt="" />
  </div>
  <div class="data">
    <h4 class="number inline-block">{social_media_number}</h4>
    <span class="right">
      <Stat number={data_number} icon={data_icon} />
    </span>
  </div>
</div>
