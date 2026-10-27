<script>
  let { isOn, onToggle } = $props();
</script>

<div 
    class="cell"
    role="button"
    tabindex="0"
    onclick={onToggle}
    onkeydown={(event) => {
        if (event.key === 'Enter' || event.key === ' ') {
            event.preventDefault();
            onToggle();
        }
    }}
    style:background-color={isOn ? 'black' : 'white'}
></div>

<style>
  .cell {
    width: 100px;
    height: 100px;
    border: 1px solid grey;
    box-sizing: border-box;
  }
</style>