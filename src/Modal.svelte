<script>
export let show=true;
// it is mandatory to declare prop name using export

</script>
{#if show}
<div>
<div>
<!-- only defining onclick will forward event to parent component where it is called example inside </Modal> -->
<!-- | self is event modifier -->
<div on:click|self>
<slot></slot>
<!-- this firstsl is name of the slot -->
<slot name='firstsl'></slot>
</div>
</div>
</div>
{/if}
<style>

</style>