<script lang="ts">
  export let display: string
</script>

<button on:click>{display}</button>

<style>
  button {
    height: var(--btheight);
    display: flex;
    justify-content: center;
    align-items: center;
    background: var(--yellow);
    color: var(--black);
    border-radius: var(--btradius);
    font-weight: 800;
    font-size: var(--font14);
  }
</style>