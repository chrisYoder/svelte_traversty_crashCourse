<script>
  import Navbar from "./Navbar.svelte";
  import Player from "./Player.svelte";
  import AddPlayer from "./AddPlayer.svelte";

  let players = [
    {
      name: "Chris Yoder",
      points: 53
    },
    {
      name: "Emily Yoder",
      points: 60
    },
    {
      name: "Orion Yoder",
      points: 51
    },
    {
      name: "Arya Yoder",
      points: 75
    }
  ];

  const addPlayer = e => {
    const newPlayer = e.detail;
    players = [...players, newPlayer];
  };

  const removePlayer = e => {
    players = players.filter(player => player.name !== e.detail);
  };
</script>



<Navbar />
<div class='container'>
  <h3>Add Player</h3>
      <AddPlayer 
        on:addplayer={addPlayer}
      />
  {#if players.length === 0}
    <p>No Players</p>
  {:else}
    {#each players as player}
      <Player 
        name={player.name}
        points={player.points}
        on:removeplayer={removePlayer}
      /> 
    {/each}
      
  {/if}
  
</div>




