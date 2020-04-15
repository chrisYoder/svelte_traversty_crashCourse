<script>
  import { createEventDispatcher } from "svelte";

  const dispatch = createEventDispatcher();
  let player = {
    name: "",
    points: 0
  };

  const onSubmit = e => {
    e.preventDefault();
    dispatch("addplayer", player);
    player = {
      name: "",
      points: 0
    };
  };
</script>

<style>

</style>

<!-- Templating goes here -->
<form class='grid-3' on:submit={onSubmit}>
  <input type="text" placeholder="Player Name" bind:value={player.name}>
  <input type="text" placeholder="Player Points" bind:value={player.points}>
  <input type="submit" class='btn btn-primary' value='Add Player'>

</form>