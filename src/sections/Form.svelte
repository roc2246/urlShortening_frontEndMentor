<script>
  import Button from "../components/Button.svelte";
  import URL from "../components/URL.svelte";

  let shortURLs = [];

  const shortener = (url) => {

    const domainRegex = /(?<=:\/\/).*?([^com]+)/g;
    const pathRegex = /^[^\.]+\.(.+\..+)$/;
    let newURL = url.match(domainRegex, "reLink");
    // newURL = url.replace(pathRegex, "1246")
    newURL = JSON.stringify(newURL);
    newURL = newURL.replace('["', "");
    newURL = newURL.replace('"]', "");

    const urlObject ={
        before: url, 
        after: newURL
    }

    shortURLs = [...shortURLs, urlObject];
    console.log(urlObject)
    console.log(shortURLs)
  };
  const isURL = () => {
    const input = document.getElementsByClassName("url--before")[0].value;
    const URLRegex =
      /[-a-zA-Z0-9@:%._\+~#=]{1,256}\.[a-zA-Z0-9()]{1,6}\b([-a-zA-Z0-9()@:%_\+.~#?&//=]*)?/gi;
    if (input.match(URLRegex)) {
      console.log(input);
      shortener(input);
    } else {
      console.log("NO");
    }
  };
</script>

<form class="shortener" action="" on:submit|preventDefault>
  <input type="text" name="" id="" class="url--before" />
  <Button on:click={() => isURL()}>Shorten It!</Button>
</form>
