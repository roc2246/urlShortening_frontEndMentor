<script>
  import Button from "../components/Button.svelte";
  import URL from "../components/URL.svelte";

  let shortURLs = [];

  const shortener = (url) => {

    const domainRegex = /(?<=www\.)(.*?)(?=\.[a-z])/;
    const pathRegex = /(?<=\.*\/).*$/;
    let newURL = url.replace(domainRegex, "reLink");
    newURL = newURL.replace(pathRegex, "1246")
    newURL = JSON.stringify(newURL);
    newURL = newURL.replace('["', "");
    newURL = newURL.replace('"]', "");

    const urlObject ={
        before: url, 
        after: newURL
    }

    shortURLs = [...shortURLs, urlObject];
  };

  const isURL = () => {
    const input = document.getElementsByClassName("url--before")[0].value;
    const URLRegex =
      /[-a-zA-Z0-9@:%._\+~#=]{1,256}\.[a-zA-Z0-9()]{1,6}\b([-a-zA-Z0-9()@:%_\+.~#?&//=]*)?/gi;
    if (input.match(URLRegex)) {
      shortener(input);
    } else {
      console.log("NO");
    }
  };
</script>

<form class="shortener" action="" on:submit|preventDefault>
  <input type="text" name="" id="" class="url--before" />
  <Button className="btn" on:click={() => isURL()}>Shorten It!</Button>
</form>

{#each shortURLs as url, i}
<URL before={url.before} after={url.after} btnID={i}/>
{/each}
