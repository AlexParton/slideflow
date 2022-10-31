<script lang="ts">
	import { createEventDispatcher } from "svelte";


  export let name: string
  export let value: string = ''
  export let label: string = ''

  const dispatch = createEventDispatcher();

  let focused: boolean = false;

  const blurHandler = (): void => {
    focused = false
    dispatch('value', {value: value})
  }
</script>

<div class={(focused) ? 'focused' : ''}>
  <label for={name}>{label}</label>
  <input type="text" name={name} bind:value={value} on:focus={() => focused = true} on:blur={blurHandler}/>
  {#if value !== ''}
    <button on:click={() => value = ''}>x</button>
  {/if}
  
</div>

<style>
  div {
    display: grid;
    grid-template-columns: 1fr;
    gap: 1vw;
    font-size: var(--font14);
    position: relative;
  }
  input { 
    height: var(--btheight);
    border-bottom: 1px solid var(--darkgrey);
    font-size: var(--font16);
    text-align-last: left;
    color: var(--grey)
  }

  input:focus {
    border-bottom: 1px solid var(--yellow);
  }

  button {
    position: absolute;
    bottom: 2vw;
    right: -3vw;
    width: 10vw;
    height: 10vw;
    font-size: var(--font25);
    border-radius: 100%;
    background: #2726265c;
    backdrop-filter: blur(2px);
    color: var(--warning);
  }
  
  .focused label {
    color: var(--yellow)
  }
</style>