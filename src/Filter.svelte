<script lang="ts">
  export let filter = '';
  export let label;
</script>

<div class="m-3">
  <p>{label}</p> <input class="border" bind:value={filter} />
</div>