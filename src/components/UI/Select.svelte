<script lang="ts">
	import { createEventDispatcher } from "svelte";
  export let name: string
  export let value: string = ''
  export let label: string = ''
  export let options: {value: string, display: string}[];

  let focused: boolean = false;

  const dispatch = createEventDispatcher();

  const blurHandler = (): void => {
    focused = false
    dispatch('value', {value: value})
  }
</script>

<div class={(focused) ? 'focused' : ''}>
  <label for={name}>{label}</label>
  <select name={name} bind:value={value} on:focus={() => focused = true}  on:blur={blurHandler}>
    {#each options as option}
      <option value={option.value}>{option.display}</option>
    {/each}
  </select>

</div>

<style>
  div {
    display: grid;
    grid-template-columns: 1fr;
    gap: 1vw;
    font-size: var(--font14);
    position: relative;
  }
  select { 
    height: var(--btheight);
    border-bottom: 1px solid var(--darkgrey);
    font-size: var(--font16);
    text-align-last: left;
    color: var(--grey)
  }

  select:focus {
    border-bottom: 1px solid var(--yellow);
  }

  .focused label {
    color: var(--yellow)
  }
</style>