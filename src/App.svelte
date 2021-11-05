<script>
	import List from "./List.svelte";
import list from "./List.svelte"
</script>

<main>
	<div id="grad">
		<List />
	</div>
</main>

<style>
	main {
		text-align: center;
		
		max-width: 240px;
		
	}
	#grad {
		margin-top: -60px;
  		background-image: linear-gradient(to right, rgba(255,0,0,0), #A683E3);
  		width: 100vw;
  		height: 100vw;
		padding-top: 100px;
		
}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>