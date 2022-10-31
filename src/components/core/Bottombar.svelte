<script>
  import { createEventDispatcher } from 'svelte';
  const dispatch = createEventDispatcher();
</script>

<section>
  <button  on:click={() => dispatch('feed')}>
    <img src="/icons/home.svg" alt="home">
    <span>home</span>
  </button>
  <button>
    <img src="/icons/movie.svg" alt="movie">
    <span>create</span>
  </button>
  <div></div>
  <button class="gethelp" on:click={() => dispatch('help')}>
    <img src="/icons/help.svg" alt="info">
  </button>
  <button>
    <img src="/icons/notifications.svg" alt="notifications">
    <span>interactions</span>
  </button>
  <button>
    <img src="/icons/person.svg" alt="person">
    <span>profile</span>
  </button>
  
</section>

<style>
  section {
    position: fixed;
    bottom: 0;
    left: 0;
    width: 100%;
    height: var(--bottomHeight);
    z-index: 6;
    background: var(--black);
    display: grid;
    grid-template-columns: repeat(5, 1fr);
    gap: 5vw;
    align-items: center;
  }

  button {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-wrap: wrap;
    color: var(--darkgrey);
    font-size: var(--font8);
  }

  img {
    width: 40%;
    opacity: .6;
  }

  .gethelp {
    background:var(--black);
    width: 10vh;
    border-radius: 100%;
    height: 10vh;
    position: absolute;
    left: 0;
    right: 0;
    margin: auto;
    box-shadow: inset 0 0 0 3px rgba(255, 255, 255, 0.401);
    top: -1.5vh;
  }

  .gethelp img {
    width: 60%;
  }
  div {
    visibility: hidden;
  }
</style>