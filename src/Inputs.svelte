<script lang="ts">
  import type { Item, Skill } from './schema';
  export let inputs: Item[];
  export let skill: Skill;
  export let tool: string;

  const names = inputs.map(i => `${i['num']} ${i['name']}`);
  const skillDisplay = skill ? `${skill['name']} Level ${skill['level']}` : null;
  const combined = [...names, tool, skillDisplay].filter(n => n).join(' + ')
</script>

<td class="border border-gray-600">
  <div class="mx-1 my-1.5">
    {combined}
  </div>
</td>