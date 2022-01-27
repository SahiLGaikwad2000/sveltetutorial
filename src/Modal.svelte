<script>
export let show=true;
// it is mandatory to declare prop name using export
export let message='Sign up for offer'; 
</script>
{#if show}
<div>
<div>
<!-- only defining onclick will forward event to parent component where it is called example inside </Modal> -->
<p on:click>{message}</p>
</div>
</div>
{/if}
<style>

</style>