<script>
  import "../app.scss";
  import { theme } from "$lib/store.js";
</script>

<svelte:head>
  <link rel="stylesheet" href={`../${$theme}.scss`} />
</svelte:head>

<div class="heading">
  <a class="title" href="/">
    <div>Videos</div>
  </a>
  <a class="links main" sveltekit:prefetch href="/main">main</a>
  <a class="links" sveltekit:prefetch href="/culture">culture</a>
  <a class="links search" sveltekit:prefetch href="/search"
    ><i class="fa-solid fa-magnifying-glass" /></a
  >
</div>

<slot />

<style lang="scss">
  :global(body) {
    background-color: var(--background-color);
    font-family: "Poppins", sans-serif;
    color: var(--text-color);
  }
  .heading {
    display: flex;
    padding: 20px 20px;
    flex-wrap: wrap;
    height: 100px;
  }
  .title {
    color: var(--accent-color);
    font-size: 3em;
  }
  .main {
    margin-left: auto;
  }
  .links {
    align-self: center;
    padding: 0 30px;
    font-size: 1.25rem;
    color: var(--text-color);
  }
  .search {
    color: var(--accent-color);
    padding-right: 0;
  }
  @media only screen and (max-width: 600px) {
    .links {
      padding: 5px;
    }
  }
</style>
