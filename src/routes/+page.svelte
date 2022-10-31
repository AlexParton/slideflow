<script lang='ts'>
  import Video from "../components/video/Video.svelte";
  import Feed from '../components/core/Feed.svelte';
  import GetHelp from '../components/core/GetHelp.svelte';
  import { dummydata } from '../data/dummydata';
  import Header from '../components/core/Header.svelte';
  import Bottombar from '../components/core/Bottombar.svelte';

  let displayState = 'feed';

  const setDisplayState = (state: string): void => {
    displayState = state
  }
</script>

<Header />
<main>
  {#if displayState === 'feed'}
    <Feed>
      {#each dummydata.videos as video}
        <Video video={video} isLiked={false} isBookmarked={false}/>
      {/each}
    </Feed>
  {/if}

  {#if displayState === 'help'}
    <GetHelp />
  {/if}
</main>
<Bottombar 
  on:help={() => setDisplayState('help')}
  on:feed={() => setDisplayState('feed')}
/>
