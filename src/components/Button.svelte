<script>
    export let className;
</script>

<button class={className} on:click><slot /></button>

<style>
    button{
        white-space: nowrap;
    }


</style>
