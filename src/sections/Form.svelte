<script>
  import Button from "../components/Button.svelte";
  import URL from "../components/URL.svelte";

  let shortURLs = [];

  const shortener = (url) => {
    const randomnNo = Math.round(Math.random() * 1000);

    const domainRegex = /(?<=www\.)(.*?)(?=\.[a-z])/;
    const pathRegex = /(?<=\.*\/).*$/;
    let newURL = url.replace(domainRegex, "reLink");
    newURL = newURL.replace(pathRegex, randomnNo.toString());
    newURL = JSON.stringify(newURL);
    newURL = newURL.replace('"', "");
    newURL = newURL.replace('"', "");

    console.log(newURL);

    const urlObject = {
      before: url,
      after: newURL,
    };

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
    document.getElementsByClassName("url--before")[0].value = "";
  };
</script>

<section class="shortener-container">
  <form class="shortener" on:submit|preventDefault>
  <input type="text" name="" id="" class="url--before" />
  <Button className="btn btn--shorten" on:click={() => isURL()}
    >Shorten It!</Button
  >
</form>
</section>


{#each shortURLs as url, i}
  <URL before={url.before} after={url.after} btnID={i} />
{/each}

<style lang="scss">
  @import "../scss/global";
  .shortener-container{
    background: linear-gradient(to bottom,  white 50%,$gray 50%,);
  }
  .shortener {
    margin-right: min(10rem, 5%);
    margin-left: min(10rem, 5%);
    background-image: url("/images/bg-boost-desktop.svg");
    background-color: $very-dark-blue;
    border-radius: .25rem;
    padding: 2rem;
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    justify-content: space-between;
  }
  .url--before {
    width: 75%;
  }
  @media (max-width: 375px){
    .url--before {
    width: 100%;
  }
}
</style>
