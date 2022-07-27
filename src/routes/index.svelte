<script>
  let movies = ["movie-1", "movie-2"];
  let anime = [1, 2, 3, 4];
</script>

<!-- <div class="main">
  <div class="main-1">
  </div>
  <div class="main-2">

  </div>
</div> -->

<div class="container">
  <div class="section">
    <!-- <h1>Main</h1> -->
    <div class="main-grid">
      {#each movies as movie}
        <div class="flex">
          <img src={`/${movie}.jpg`} alt={movie} />
          <div class="sub-flex">
            <p>{movie}</p>
            <button class="left button-24"
              ><i class="fa-solid fa-display" /></button
            >
            <button class="button-24"
              ><i class="fa-solid fa-mobile-screen" /></button
            >
          </div>
        </div>
      {/each}
    </div>
  </div>
  <div class="section">
    <!-- <h1>Anime</h1> -->

    <div class="culture-grid">
      {#each anime as ani}
        <div class="flex">
          <img src={`/anime-${ani}.jpg`} alt={"anime"} />
          <div class="sub-flex">
            <p>{`anime-${ani}`}</p>
            <button class="left button-24"
              ><i class="fa-solid fa-display" /></button
            >
            <button class="button-24"
              ><i class="fa-solid fa-mobile-screen" /></button
            >
          </div>
        </div>
      {/each}
    </div>
  </div>
</div>

<style lang="scss">
  .container {
    height: calc(100vh - 100px);
    scroll-snap-type: y mandatory;
    overflow: auto;
    .section {
      height: calc(100vh - 100px);
      display: flex;
      /* justify-content: center; */
      align-items: center;
      scroll-snap-align: center;
      margin: 20px 0;
    }
  }
  /* .main {
    display: flex;
  }
  .main-1 {
    height: calc(100vh - 100px);
    width: 100%;
  } */
  /* h1 {
    color: var(--accent-color);
    padding: 20px;
    font-size: 2.5rem;
  } */
  .main-grid {
    display: grid;
    grid-template-columns: repeat(2, minmax(0, 1fr));
    margin: 0 20px;
    gap: 20px;
  }
  .culture-grid {
    display: grid;
    grid-template-columns: repeat(4, minmax(0, 1fr));
    margin: 0 20px;
    gap: 20px;
  }
  .flex {
    display: flex;
    flex-direction: column;
    img {
      width: 100%;
      border-radius: 0.25rem;
    }
  }
  .sub-flex {
    display: flex;
    p {
      padding: 20px 0;
      font-size: 1.25rem;
    }
  }
  .button-24 {
    background: var(--accent-color);
    border: 1px solid var(--accent-color);
    border-radius: 6px;
    box-shadow: rgba(0, 0, 0, 0.1) 1px 2px 4px;
    color: var(--text-color);
    cursor: pointer;
    font-size: 1.25rem;
    padding: 10px 20px;
    align-self: center;
    height: fit-content;
    text-align: center;
    touch-action: manipulation;
    transition: all 300ms cubic-bezier(0.23, 1, 0.32, 1);
  }

  .button-24:hover,
  .button-24:active {
    background-color: initial;
    background-position: 0 0;
    color: var(--accent-color);
  }

  .button-24:active {
    opacity: 0.5;
  }
  .left {
    margin-left: auto;
    margin-right: 10px;
  }
  @media only screen and (max-width: 600px) {
    .main-grid {
      grid-template-columns: repeat(1, minmax(0, 1fr));
    }
    .culture-grid {
      grid-template-columns: repeat(1, minmax(0, 1fr));
    }
  }
</style>
