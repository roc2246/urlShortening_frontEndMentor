<script>
  export let navMode;
</script>

<nav class={navMode}>
  <section class="nav__main">
    <div class="nav__img-box">
      <img src="images/logo.svg" alt="Shortly Logo" />
    </div>
    <a href="blank" class="nav__main--link">Features</a>
    <a href="blank" class="nav__main--link">Pricing</a>
    <a href="blank" class="nav__main--link">Resources</a>
  </section>
  <section class="nav__users">
    <a href="blank" class="nav__users--login">Login</a>
    <button class="btn nav__users--register">Sign Up</button>
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
      @include flexRow();
    }
    &__main {
      @include flexRow();
      flex-wrap: wrap;
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
