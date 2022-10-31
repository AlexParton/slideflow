<script>
  import Header from '../components/core/Header.svelte';
  import Bottombar from '../components/core/Bottombar.svelte';
</script>

<Header />
<main>
  <slot />
</main>
<Bottombar />