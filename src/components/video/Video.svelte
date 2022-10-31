<script lang="ts">
	import InfoPanel from "./InfoPanel.svelte";
  import InteractionMenu from "./InteractionMenu.svelte";
  import type { VideoType } from '../../types/types';
  export let video: VideoType;
  export let isLiked: boolean;
  export let isBookmarked: boolean;

  let paused: boolean = false;

  const clickHandler = (): void => {
    paused = !paused
  }

</script>
<div id={video.id}>
  <button on:click={clickHandler} class={!paused ? 'playing' : ''}>
    <img src={paused ? '/icons/pause.svg' : '/icons/play.svg'} alt="play pause">
  </button>
  <video
    loading="lazy"
    width="320"
    height="714"
    src={video.src}
    autoplay={false}
    bind:paused
    >
    <track kind="captions">
  </video>
  <InfoPanel video={video}/>
  <InteractionMenu isLiked={isLiked} isBookmarked={isBookmarked}/>
</div>

<style>
  div {
    height: 100vh;
    scroll-snap-align: start;
    width: 100%;
    position: relative;
  }
  video {
    height: 100%;
    width: auto;
    z-index: 1;
  }

  button {
    position: absolute;
    width: 100%;
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    z-index: 2;
  }

  button img {
    max-width: 50%;
  }

  button.playing img {
    opacity: 0;
    transition: .6s;
  } 
</style>