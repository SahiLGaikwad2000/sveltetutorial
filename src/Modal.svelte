<script>
let show=true;
// it is mandatory to declare prop name using export
export let message='Sign up for offer'; 
</script>
{#if show}
<div>

<p>{message}</p>
</div>
{/if}
<style>

</style>