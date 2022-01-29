<script>
	import Modal from './Modal.svelte';
	import Addperson from './Newperson.svelte';
	let people=[
		{name:'sahil',code:100,id:1},
		{name:'tushar',code:101,id:2},
		{name:'riddhi',code:102,id:3}
	];
	const handleClick=(id)=>{
		people=people.filter((person)=>person.id!=id)

	}
	let show=false;
	const handleshow=()=>{
		show=!show;
	}
	const addPerson=(e)=>{
		const person=e.detail
		console.log(person)
		people=[person,...people]
		show=false;
;
	}
</script>
<!-- here message is string prop . props can be of various types like object,int -->
<!-- You can add more contents in modal component in opening and closing tag -->
<!-- slots are used for this. Named slots are used for reference example div tag has named slot -->
<Modal {show} on:click={handleshow}>
<Addperson on:addPerson={addPerson}/>

</Modal> 
<main>
	<div>
		{#each people as person}
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
		<div>
			<!-- |once is event modifier -->
			<button on:click={handleshow}>Show modal</button>
		</div>
	</div>
</main>


<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	/* h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	} */

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>