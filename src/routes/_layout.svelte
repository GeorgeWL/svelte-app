<script>
	import Nav from '../components/Nav.svelte';

	export let segment;
</script>

<style>
  
	main {
    width: 100%;
		position: relative;
		max-width: 56em;
		background-color: white;
		padding: 2em;
		box-sizing: border-box;
	}
  @media (max-width:550px){
    main{
      margin: 0 auto;
    }
  }
</style>

<Nav {segment}/>

<main>
	<slot></slot>
</main>
