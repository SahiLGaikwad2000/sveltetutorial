<script>
	let people=[
		{name:'sahil',code:100,id:1},
		{name:'tushar',code:101,id:2},
		{name:'riddhi',code:102,id:3}
	];
	const handleClick=(id)=>{
		people=people.filter((person)=>person.id!=id)

	}
</script>

<main>
	<div>
		{#each people as person (person.id)}
		<div>
			{#if person.code===102}	
			<p><strong>James Bond</strong></p>
			{/if}
		<h4>{person.name} {person.code}</h4>
		<button on:click={()=>{handleClick(person.id)}}>Delete</button> 
		<!-- used inline function to pass reference of function handleclick so that it gets called only when button is clicked -->
	</div>
		{:else}
		<h4>There are no people to show.</h4>	
		
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