<script>
  import Button from "../components/Button.svelte";
  import URL from "../components/URL.svelte";

  let displayError = false;

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

    const urlObject = {
      before: url,
      after: newURL,
    };

    shortURLs = [...shortURLs, urlObject];
  };

  const isURL = () => {
    const inputBox = document.getElementsByClassName("url--before")[0];
    const input = inputBox.value;
    const URLRegex =
      /[-a-zA-Z0-9@:%._\+~#=]{1,256}\.[a-zA-Z0-9()]{1,6}\b([-a-zA-Z0-9()@:%_\+.~#?&//=]*)?/gi;
    if (input.match(URLRegex)) {
      shortener(input);
      displayError = false;
    } else {
      inputBox.style.borderColor = "hsl(0, 87%, 67%)";
      displayError = true;
    }
    inputBox.value = "";
  };
</script>

<section class="shortener-container">
  <form class="shortener" on:submit|preventDefault>
    <div class="insert-url">
      <input
        type="text"
        placeholder="Shorten a link here..."
        class="url--before"
      />
      {#if displayError === true}
        <p class="shortener__error-message">Please <i>add</i> a link</p>
      {/if}
    </div>

    <div class="button-container">
      <Button className="btn btn--shorten" on:click={() => isURL()}
        >Shorten It!</Button
      >
    </div>
  </form>
</section>

<section class="url-container">
  {#each shortURLs as url, i}
    <URL before={url.before} after={url.after} btnID={i} />
  {/each}
</section>

<style lang="scss">
  @import "../scss/global";
  .shortener-container {
    background: linear-gradient(to bottom, white 50%, $gray 50%);
  }
  .shortener {
    margin-right: min(10rem, 5%);
    margin-left: min(10rem, 5%);
    background-image: url("/images/bg-boost-desktop.svg");
    background-color: $very-dark-blue;
    border-radius: 0.25rem;
    padding: 2rem;
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    justify-content: space-between;
    height: 2.5rem;
    .insert-url {
      display: flex;
      flex-direction: column;
      width: 80%;
    }
    &__error-message {
      margin-top: 0;
      color: $red;
    }
  }
  .url-container {
    background-color: $gray;
    padding-top: 1rem;
    padding-bottom: 1rem;
  }
  @media (max-width: 1090px) {
    .shortener {
      height: auto;

    }
  }
  @media (max-width: 375px) {
    .shortener {
      height: auto;
      .insert-url {
        width: 100%;
      }
      .button-container {
        width: 100%;
      }
    }
  }
</style>
