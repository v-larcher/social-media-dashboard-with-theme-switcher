<script>
  function toggle() {
    window.document.body.classList.toggle("dark-mode");
    background_color =
      "linear-gradient(to right, hsl(210, 78%, 56%) 0%, hsl(146, 68%, 55%) 100%)";
  }
  let background_color = "hsl(230, 22%, 74%)";
</script>

<style>
  .container {
    float: right;
    margin: -30px 50px 10px 0px;
  }
  @media only screen and (min-width: 400px) {
    hr {
      display: none;
    }
  }
  @media only screen and (max-width: 376px) {
    .container {
      float: none;
      margin: -20px 0px 40px 0px;
      padding: 0px 0px 0px 0px;
    }
    .switch {
      margin-left: 195px;
    }
  }

  .center {
    display: inline-block;
    margin-bottom: 17px;
  }

  .text {
    display: inline-block;
    font-size: 13.5px;
    font-weight: bold;
    color: hsla(228, 12%, 44%, 0.85);
    margin-right: 6px;
  }

  :global(body.dark-mode) .text {
    color: hsl(228, 34%, 66%);
  }

  /* The switch - the box around the slider */
  .switch {
    position: absolute;
    width: 50px;
    height: 25px;
  }

  /* Hide default HTML checkbox */
  .switch input {
    opacity: 0;
    width: 0;
    height: 0;
  }

  /* The slider */
  .slider {
    position: absolute;
    cursor: pointer;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background-color: hsl(230, 22%, 74%);

    -webkit-transition: 0.5s;
    transition: 0.5s;
  }

  .slider:before {
    position: absolute;
    content: "";
    height: 18.4px;
    width: 18.4px;
    left: 28.2px;
    bottom: 3.7px;
    background-color: hsl(225, 100%, 98%);
    -webkit-transition: 0.5s;
    transition: 0.5s;
  }
  :global(body.dark-mode) .slider:before {
    position: absolute;
    content: "";
    height: 18.5px;
    width: 18.5px;
    left: 3px;
    bottom: 3.7px;
    background-color: hsl(232, 19%, 15%);
    -webkit-transition: 0.5s;
    transition: 0.5s;
  }

  .slider {
    background: var(--background-color);
  }

  /* Rounded sliders */
  .slider.round {
    border-radius: 20px;
  }
  .slider.round:before {
    border-radius: 50%;
  }

  hr {
    border: 1px solid hsla(229, 12%, 44%, 0.5);
    margin-bottom: 18px;
  }
  :global(body.dark-mode) hr {
    border: 1px solid hsla(228, 34%, 66%, 0.25);
  }
</style>

<div class="container">
  <hr />
  <div class="text">Dark Mode</div>
  <div class="center">
    <label class="switch">
      <input type="checkbox" on:click={toggle} />
      <span
        style="--background-color: {background_color}"
        class="slider round"><slot /></span>
    </label>
  </div>
</div>
