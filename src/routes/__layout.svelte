<script>
  import "../app.scss";
</script>

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
  .heading {
    display: flex;
    padding: 20px 20px;
    flex-wrap: wrap;
    height: 15vh;
  }
  .title {
    color: $accent;
    font-size: 3em;
  }
  .main {
    margin-left: auto;
  }
  .links {
    align-self: center;
    padding: 0 30px;
    font-size: 1.25rem;
    color: $font;
  }
  .search {
    color: $accent;
    padding-right: 0;
  }
  @media only screen and (max-width: 600px) {
    .links {
      padding: 5px;
    }
  }
</style>
