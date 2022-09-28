<script>
  import Button from "../components/Button.svelte";
  export let navMode;
</script>

<nav class={navMode}>
  <div class="nav__img-box">
    <img src="images/logo.svg" alt="Shortly Logo" />
  </div>
  <section class="nav__main">
    <a href="blank" class="nav__main--link">Features</a>
    <a href="blank" class="nav__main--link">Pricing</a>
    <a href="blank" class="nav__main--link">Resources</a>
  </section>
  <section class="nav__users">
    <a href="blank" class="nav__users--login">Login</a>
    <Button className="btn btn--signup">Sign Up</Button>
  </section>
</nav>

<style lang="scss">
  @import "../scss/global";

  .nav {
    &--desktop {
      display: flex;
      flex-direction: row;
      flex-wrap: wrap;
      margin-left: min(10rem, 5%);
      margin-right: min(10rem, 5%);
    }
    &__img-box {
      margin-right: 1rem;
    }
    &__main {
      display: flex;
      flex-direction: row;
      flex-wrap: wrap;
      margin-left: 1rem;
      & > * {
        margin-right: 2rem;
        color: $grayish-violet;
        font-weight: $fontweight-heavy;
      }
    }
    &__users {
      margin-left: auto;
      & > * {
        margin-right: 2rem;
      }
      & > a {
        color: $grayish-violet;
        font-weight: $fontweight-heavy;
      }
    }
  }
</style>
