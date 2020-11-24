<script lang="ts">
  import Tailwind from "./Tailwind.svelte";
  import Blueprints from "./Blueprints.svelte";
  import Filter from "./Filter.svelte";
  import blueprints from "./resources/blueprints";

  $: outputFilter = '';
  $: inputFilter = '';
  $: filteredBlueprints =
    blueprints
      .flatMap(blueprint => blueprint['recipes'])
      .filter( recipe => new RegExp(outputFilter, 'i').test(recipe['output']['name']))
      .filter( recipe => recipe['inputs'].filter( input => new RegExp(inputFilter, 'i').test(input['name'])).length)
</script>

<Tailwind />

<Filter label='Filter Outputs' bind:filter={outputFilter}/>
<Filter label='Filter Inputs' bind:filter={inputFilter}/>
<div class="flex justify-center m-3">
  <Blueprints recipes={filteredBlueprints}/>
</div>
