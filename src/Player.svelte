<script>
 export let name;
 export let points;

 import { createEventDispatcher } from "svelte";
 const dispatch = createEventDispatcher();

 let showControls = true;

 const addPoint = () => (points += 1);
 const removePoint = () => (points -= 1);
 const toggleControls = () => (showControls = !showControls);
 const onDelete = () => dispatch("removeplayer", name);
</script>

<style>
  h1 {
    color: var(--primary-color);
  }

  h3 {
    margin-bottom: 10px;
  }
</style>

<!-- Templating goes here -->

<div class='card'>
  <h1>
    {name}      
    <button 
      class='btn btn-sm' 
      on:click={toggleControls}
    >
      {#if showControls}
        -
      {:else}
        +
      {/if}
    </button>
    <button 
      class='btn btn-sm btn-danger'
      on:click={onDelete}
    >x</button>
  </h1>
  <h3>Points: {points}</h3>
  {#if showControls}
    <button class='btn' on:click={addPoint}>+1</button>
    <button class='btn btn-dark' on:click={removePoint}>-1</button>
    <input type="number" bind:value={points}>
  {/if}
</div>
