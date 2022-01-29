<script>
    
import { createEventDispatcher } from 'svelte';
let dispatch=createEventDispatcher();
let name;
let age;
let beltcolour;
let skills=[];
let code=105;
const handlesubmit=()=>{
    // console.log(name,age,skills,beltcolour)
    let person={
        name,
        age,beltcolour,code
    }
    dispatch('addPerson',person)
    code=code+1
}
</script>
<!-- preventdefault is event modifer so that it prevents refreshing page after submitting -->
<!-- bind group is used to bind values together-->

<form on:submit|preventDefault={handlesubmit}>
    <input type="text" placeholder="name" bind:value={name}>
    <input type="text" placeholder="Age" bind:value={age}>
    <label>Skills:</label>
    <input type='checkbox' value='fighting' bind:group={skills}> fighting<br>
    <input type='checkbox' value='seeking' bind:group={skills}> seeking<br>
    <input type='checkbox' value='running' bind:group={skills}> running<br>
    <select bind:value={beltcolour}>
        <option value='black'>black</option>
        <option value='blue'>blue</option>
        <option value='brown'>brown</option>
    </select>
    <button>Submit</button>

</form>
<style>

</style>