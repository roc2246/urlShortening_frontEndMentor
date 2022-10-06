<script>
  import Button from "./Button.svelte";
  import { cubicIn } from "svelte/easing";
  import { fly } from "svelte/transition";

  export let before;
  export let after;

  const copyBtn = document.getElementsByClassName("btn--copy");
  export let btnID;

  const copyURL = (url, btnID) => {
    navigator.clipboard.writeText(url);
    for (let x = 0; x < copyBtn.length; x++) {
      if (copyBtn[x].innerText === "Copied!") {
        copyBtn[x].innerText = "Copy";
        copyBtn[x].style.backgroundColor = "hsl(180, 66%, 49%)";
      }
    }
    copyBtn[btnID].innerText = "Copied!";
    copyBtn[btnID].style.backgroundColor = "hsl(257, 27%, 26%)";
  };
</script>

<div class="shortened-url" transition:fly={{ easing: cubicIn, x: 0, y: 300 }}>
  <div class="shortened-url__container">
    <span class="shortened-url--before">{before}</span>
    <hr class="shortened-url__break" />
    <span class="shortened-url--after">{after}</span>
    <Button className="btn btn--copy" on:click={() => copyURL(after, btnID)}
      >Copy</Button
    >
  </div>
</div>

<style lang="scss">
  @import "../scss/global";
  .shortened-url {
    background-color: $gray;
    margin-top: 1rem;
    &__container {
      display: flex;
      flex-direction: row;
      border-radius: 0.75rem;
      padding: 1rem;
      background-color: white;
      margin-right: min(10rem, 5%);
      margin-left: min(10rem, 5%);
    }
    &--before {
       word-break: break-all;
      font-weight: $fontweight-light;
      margin-top: .5rem;
      margin-right: 1rem;

    }
    &__break {
      display: none;
      width: 100%;
    }
    &--after {
       word-break: break-all;
      color: $cyan;
      font-weight: $fontweight-light;
      margin-left: auto;
      margin-right: 1rem;
      margin-top: .5rem;
    }
  }

  @media (max-width: $mobile) {
    .shortened-url {
      &__container {
        flex-direction: column;
      }
      &--before {
        margin-right: auto;
      }
      &__break {
        display: block;
      }
      &--after {
        margin-left: 0;
        margin-right: auto;
        margin-bottom: 1rem;
      }
      & > * {
        text-align: center;
      }
    }
  }
</style>
