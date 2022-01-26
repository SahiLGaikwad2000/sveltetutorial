<script>
	export let name;
	let beltColor='black'
	let firstname=''
	let lastname=''
	const handleclick=()=>{
		beltColor='yellow'


	};
	const handleinput=(e)=>{
		beltColor=e.target.value;

	};
	$:fullname=`${firstname} ${lastname}`;
	
</script>

<main>
	<h1>Hello {name}!</h1>
	<p>{fullname}</p>
	<!-- <button on:click={handleclick}>Update belt color</button> -->
	<!-- <input type="text" on:input={handleinput} value={beltColor}> -->
	<input type="text" bind:value={beltColor}>
	<input type="text" bind:value={firstname}>
	<input type="text" bind:value={lastname}>
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