<script>
  import Stat from "./Stat.svelte";

  export let social_media_username;
  export let social_media_icon;
  export let social_media_number;
  export let color_social_media_begin;
  export let color_social_media_end;
  export let type;
  export let data_icon;
  export let data_number;
</script>

<style>
  .container {
    background: linear-gradient(
      to bottom,
      var(--color-social-media-begin) 0%,
      var(--color-social-media-end) 2%,
      hsl(227, 47%, 96%) 2%,
      hsl(227, 47%, 96%) 100%
    );
    background-color: hsl(227, 47%, 96%);
    text-align: center;
    padding-top: 20px;
    padding-bottom: 20px;
    border-radius: 3%;
  }
  .container:hover {
    background: linear-gradient(
      to bottom,
      var(--color-social-media-begin) 0%,
      var(--color-social-media-end) 2%,
      hsl(227, 37%, 90%) 2%,
      hsl(227, 37%, 90%) 100%
    );
  }
  :global(body.dark-mode) .container {
    background: linear-gradient(
      to bottom,
      var(--color-social-media-begin) 0%,
      var(--color-social-media-end) 2%,
      hsl(228, 28%, 20%) 2%,
      hsl(228, 28%, 20%) 100%
    );
  }
  .social-media {
    text-align: center;
  }
  .social-media-icon {
    display: inline-block;
  }
  .number {
    font-size: 54px;
    color: hsl(230, 17%, 14%);
    margin-top: 15px;
    margin-bottom: 0px;
  }
  :global(body.dark-mode) .number {
    color: white;
  }
  .type {
    font-size: 12px;
    letter-spacing: 5px;
    color: hsl(228, 12%, 44%);
    margin-top: 0px;
    margin-bottom: 20px;
  }
  .social-media-username {
    display: inline-block;
    position: static;
    font-size: 12.5px;
    font-weight: bold;
    margin-left: 4px;
    color: hsl(228, 12%, 44%);
  }
  :global(body.dark-mode) .type,
  :global(body.dark-mode) .social-media-username {
    color: hsl(228, 34%, 66%);
  }
  img {
    margin-bottom: -2px;
  }
</style>

<div
  class="container"
  style="--color-social-media-begin: {color_social_media_begin}; --color-social-media-end: {color_social_media_end}">
  <div class="social-media">
    <img
      class="social-media-icon"
      src="/assets/icon-{social_media_icon}.svg"
      alt="" />
    <div class="social-media-username">{social_media_username}</div>
  </div>
  <h1 class="number">{social_media_number}</h1>
  <div class="type">{type}</div>
  <div class="data">
    <Stat number={data_number} icon={data_icon} />
  </div>
</div>
