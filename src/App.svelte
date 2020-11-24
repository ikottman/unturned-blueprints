<script lang="ts">
  import Tailwind from "./Tailwind.svelte";
  import Blueprints from "./Blueprints.svelte";
  import blueprints from "./resources/blueprints";
</script>

<Tailwind />

<div class="flex justify-center m-3">
  <Blueprints blueprints={blueprints}/>
</div>
