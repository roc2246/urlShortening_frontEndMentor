<script>
import Button from "./Button.svelte"

export let before
export let after

const copyURL = (url) =>{
    let copiedURL = Object.values(url)
    copiedURL = JSON.stringify(copiedURL)
    copiedURL = copiedURL.replace('["', "");
    copiedURL = copiedURL.replace('"]', "");

    navigator.clipboard.writeText(copiedURL);
}
</script>

<div class="shortened-url">
    <span class="shortened-url--before">{before}</span>
    <span class="shortened-url--after">{after}</span>
    <Button className="btn btn--copy" on:click={()=>copyURL({after})}>Copy</Button>
</div>