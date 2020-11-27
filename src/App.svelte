<script lang="ts">
  import Tailwind from "./Tailwind.svelte";
  import Blueprints from "./Blueprints.svelte";
  import blueprints from "./resources/blueprints";
  import { ingredientsFilter, outputFilter } from "./store";

  $: recipes =
    blueprints
      .flatMap(blueprint => blueprint['recipes'])
      .filter( recipe => new RegExp($outputFilter, 'i').test(recipe['output']['name']))
      .filter( recipe => recipe['inputs'].filter( input => new RegExp($ingredientsFilter, 'i').test(input['name'])).length)
</script>

<Tailwind />

<div class="flex justify-center m-3">
  <Blueprints recipes={recipes}/>
</div>
