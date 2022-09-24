<script>
  import Button from "./Button.svelte";

  export let before;
  export let after;

  const copyBtn = document.getElementsByClassName("btn--copy");
  export let btnID;

  const copyURL = (url, btnID) => {
    navigator.clipboard.writeText(url);
    for (let x = 0; x < copyBtn.length; x++) {
      if (copyBtn[x].innerText === "Copied!") {
        copyBtn[x].innerText = "Copy";
      }
    }
    copyBtn[btnID].innerText = "Copied!";
  };
</script>

<div class="shortened-url">
  <span class="shortened-url--before">{before}</span>
  <span class="shortened-url--after">{after}</span>
  <Button className="btn btn--copy" on:click={() => copyURL(after, btnID)}
    >Copy</Button
  >
</div>
