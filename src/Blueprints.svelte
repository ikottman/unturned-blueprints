<script lang="ts">
  import Inputs from "./Inputs.svelte";
  import Output from "./Output.svelte";
  export let recipes;
</script>

<table class="table-auto bg-gray-100">
  <thead class="bg-gray-300 border border-gray-600">
    <tr>
      <th>Input</th>
      <th class="w-1/2">Output</th>
    </tr>
  </thead>
  <tbody>
    {#each recipes as recipe}
      <tr>
        <Inputs
          inputs={recipe['inputs']}
          tool={recipe['tool']}
          skill={recipe['skills']}
        />
        <Output output={recipe['output']}/>
      </tr>
    {/each}
  </tbody>
</table>