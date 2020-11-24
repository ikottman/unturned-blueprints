<script lang='ts'>
  import type { Item } from './schema';
  export let output: Item;
</script>

<td class="border border-gray-600">
  <div class="mx-1 my-1.5">
    {output['num']} {output['name']}
  </div>
</td>