<div>
	<h2>{quizName}</h2>
	<!-- <h4>{title}</h4>
	<input type="text" bind:value={title}> -->
  <input type="number" bind:value={a}>
  <input type="number" bind:value={b}>
  <p>{a + b}</p>
</div>


<script>
  export let quizName = "Chris Quiz";
  // export let title = "";
  let a = 0;
  let b = 0;
</script>

<style>
</style>