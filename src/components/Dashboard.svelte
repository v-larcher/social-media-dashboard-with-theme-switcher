<script>
  import Switch from "./Switch.svelte";
  import Item from "./Item.svelte";
  import BottomItem from "./BottomItem.svelte";

  const top_data = [
    {
      social_media_username: "@nathanf",
      social_media_icon: "facebook",
      social_media_number: "1987",
      color_social_media_begin: "hsl(208, 92%, 53%)",
      color_social_media_end: "hsl(208, 92%, 53%)",
      type: "FOLLOWERS",
      data_icon: "up",
      data_number: "12 Today",
    },
    {
      social_media_username: "@nathanf",
      social_media_icon: "twitter",
      social_media_number: "1044",
      color_social_media_begin: "hsl(203, 89%, 53%)",
      color_social_media_end: "hsl(203, 89%, 53%)",
      type: "FOLLOWERS",
      data_icon: "up",
      data_number: "99 Today",
    },
    {
      social_media_username: "@realnathanf",
      social_media_icon: "instagram",
      social_media_number: "11k",
      color_social_media_begin: "hsl(37, 97%, 70%)",
      color_social_media_end: "hsl(329, 70%, 58%)",
      type: "FOLLOWERS",
      data_icon: "up",
      data_number: "1099 Today",
    },
    {
      social_media_username: "Nathan F.",
      social_media_icon: "youtube",
      social_media_number: "8239",
      color_social_media_begin: "hsl(348, 97%, 39%)",
      color_social_media_end: "hsl(348, 97%, 39%)",
      type: "SUBSCRIBERS",
      data_icon: "down",
      data_number: "144 Today",
    },
  ];
  const bottom_data = [
    {
      type: "Page Views",
      social_media_icon: "facebook",
      social_media_number: "87",
      data_icon: "up",
      data_number: "3%",
    },
    {
      type: "Likes",
      social_media_icon: "facebook",
      social_media_number: "52",
      data_icon: "down",
      data_number: "2%",
    },
    {
      type: "Likes",
      social_media_icon: "instagram",
      social_media_number: "5462",
      data_icon: "up",
      data_number: "2257%",
    },
    {
      type: "Profile Views",
      social_media_icon: "instagram",
      social_media_number: "52k",
      data_icon: "up",
      data_number: "1375%",
    },
    {
      type: "Retweets",
      social_media_icon: "twitter",
      social_media_number: "117",
      data_icon: "up",
      data_number: "303%",
    },
    {
      type: "Likes",
      social_media_icon: "twitter",
      social_media_number: "507",
      data_icon: "up",
      data_number: "553%",
    },
    {
      type: "Likes",
      social_media_icon: "youtube",
      social_media_number: "107",
      data_icon: "down",
      data_number: "19%",
    },
    {
      type: "Total Views",
      social_media_icon: "youtube",
      social_media_number: "1407",
      data_icon: "down",
      data_number: "12%",
    },
  ];
</script>

<style>
  :global(body) {
    background-color: white;
    color: black;
  }
  :global(body.dark-mode) {
    background-color: hsl(230, 17%, 14%);
    color: white;
  }
  .grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
    gap: 1.5em;
  }

  .container {
    margin-left: 10%;
    margin-right: 10%;
  }
  @media only screen and (max-width: 376px) {
    .container {
      margin-left: 5%;
      margin-right: 5%;
    }
    h1 {
      font-size: 25px;
      margin: 20px 0px 2px 0px;
    }
    p {
      display: block;
      margin: -20px 0px 0px 0px;
      padding: 0px 0px 0px 0px;
    }
  }
  h1 {
    display: flex;
    margin-bottom: 5px;
    width: 100%;
    color: hsl(230, 17%, 14%);
  }
  p {
    display: inline-block;
    margin: -10px 0px 40px 0px;
    font-size: 14px;
    font-weight: bold;
    color: hsl(228, 12%, 44%);
  }

  h2 {
    margin-top: 40px;
    color: hsl(228, 12%, 44%);
  }

  :global(body.dark-mode) h1,
  :global(body.dark-mode) h2 {
    color: white;
  }
  :global(body.dark-mode) p {
    color: hsl(228, 34%, 66%);
  }

  .rectangle {
    position: absolute;
    margin: -8px 0px 0px -8px;
    width: 100%;
    height: 220px;
    z-index: -1;
    background-color: hsl(225, 100%, 98%);
    border-radius: 0px 0px 25px 25px;
  }
  :global(body.dark-mode) .rectangle {
    background: hsl(232, 19%, 15%);
  }
</style>

<div class="rectangle" />

<div class="container">
  <h1>Social Media Dashboard</h1>
  <p>Total Followers: 23,004</p>
  <Switch />

  <div class="grid">
    {#each top_data as t_data}
      <Item {...t_data} />
    {/each}
  </div>

  <h2>Overview - Today</h2>
  <div class="grid">
    {#each bottom_data as b_data}
      <BottomItem {...b_data} />
    {/each}
  </div>
</div>
