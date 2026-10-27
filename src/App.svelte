<script>
  import Cell from './Cell.svelte';
  let cells = $state([false, false, false, false]);

  function toggleCell(index) {
    cells[index] = !cells[index];
  }
  let count = $derived(cells.filter(cell => cell).length);
</script>

<main>
  <h1>Count: {count}</h1>
  <div class="grid">
    {#each cells as isOn, index (index)}
      <Cell 
        {isOn} 
        onToggle={() => toggleCell(index)}
      />
    {/each}
  </div>
</main>

<style>
  .grid {
    display: grid;
    grid-template-columns: repeat(2, 100px);
    grid-template-rows: repeat(2, 100px);
  }
</style>