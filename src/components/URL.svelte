<script>
import Button from "./Button.svelte"

export let before
export let after

const copyURL = (url) =>{
    navigator.clipboard.writeText(url);
}
</script>

<div class="shortened-url">
    <span class="shortened-url--before">{before}</span>
    <span class="shortened-url--after">{after}</span>
    <Button className="btn btn--copy" on:click={()=>copyURL(after)}>Copy</Button>
</div>