<script>
  import Button from '../components/Button.svelte'
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
    <!-- <button class="btn nav__users--register">Sign Up</button> -->
  </section>
</nav>

<style lang="scss">
  @mixin flexRow {
    display: flex;
    flex-direction: row;
  }
  @mixin nestedIndent() {
    margin-right: 2rem;
  }

  .nav {
    &--desktop {
      margin-top: 2rem;
      @include flexRow();
    }
    &__main {
      @include flexRow();
      flex-wrap: wrap;
      margin-left: 1rem;
      & > * {
        @include nestedIndent();
      }
    }
    &__users {
      margin-left: auto;
      & > * {
        @include nestedIndent();
      }
    }
  }
</style>
