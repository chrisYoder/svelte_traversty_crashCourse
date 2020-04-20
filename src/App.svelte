<script>
  import Quiz from "./Quiz.svelte";
  export let name;
</script>

<style>
  main {
    font-family: sans-serif;
  }
</style>

<main>
	<h1>Hello {name}</h1>
  
  <Quiz quizName='New Quiz'/>
  
  
</main>