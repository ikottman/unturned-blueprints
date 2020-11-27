<script lang="ts">
  import type { Item, Skill } from './schema';
  export let inputs: Item[];
  export let skill: Skill;
  export let tool: string;

  $: names = inputs.map(i => `${i['num']} ${i['name']}`);
  $: skillDisplay = skill ? `${skill['name']} Level ${skill['level']}` : null;
  $: combined = [...names, tool, skillDisplay].filter(n => n)
</script>

<td class="border border-gray-600">
  <div class="mx-1 my-1.5">
    {#each combined as input}
      {input}
      <br/>
    {/each}
  </div>
</td>