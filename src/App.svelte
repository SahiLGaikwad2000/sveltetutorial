<script>
	let people=[
		{name:'sahil',code:100},
		{name:'tushar',code:101},
		{name:'riddhi',code:102}
	];
	
</script>

<main>
	<div>
		{#each people as person}
			<h4>{person.name} {person.code}</h4>
			
			
		
		{/each}
	</div>
</main>


<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>