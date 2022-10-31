<script lang="ts">
	import Input from "../UI/Input.svelte";
	import Select from "../UI/Select.svelte";
  import { languageOptions } from '../../data/dummydata';
	import Button from "../UI/Button.svelte";

  let queryValue: string | null = '';
  let langValue: string | null = '';

  const findHelp = (): void => {
    console.log({queryValue}, {langValue})
  }

</script>
<section>
  <Input name="query" label="What do you need?" on:value={(event) => queryValue = event.detail.value}/>
  <Select options={languageOptions} name="language" label="What language is about?" on:value={(event) => langValue = event.detail.value}/>
  <!-- <Input name="tags" label="Add some tags? (coma separated values)"/> -->
  <Button display="FIND HELP" on:click={findHelp}/>
</section>

<style>
  section {
    color: var(--darkgrey);
    display: flex;
    justify-content: center;
    align-items: flex-start;
    padding: var(--padding);
    gap: 10vw;
    flex-wrap: wrap;
    margin-top: 20vw;
  }
</style>