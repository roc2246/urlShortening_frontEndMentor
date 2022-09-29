<script>
  import Button from "../components/Button.svelte";

  const mobileToggle = () => {
    const mainNav = document.getElementsByClassName("nav__main")[0]
    const userNav = document.getElementsByClassName("nav__users")[0]
    const isempty = mainNav.style.display === "" && userNav.style.display === ""

    if(isempty){
      mainNav.style.display = "flex"
      userNav.style.display = "flex"
    } else {
      mainNav.style.display = ""
      userNav.style.display = ""
    }
  }
</script>

<nav class="nav">
  <section class="nav__img-box">
    <img src="images/logo-top.svg" alt="Shortly Logo" />
  </section>
  <section class="nav__mobile-toggle" on:click={()=> mobileToggle()}>
    <img src="images/icon-menu.svg" alt="Toggle">
  </section>
  <section class="nav__main">
    <a href="blank" class="nav__main--link">Features</a>
    <a href="blank" class="nav__main--link">Pricing</a>
    <a href="blank" class="nav__main--link">Resources</a>
  </section>
  <section class="nav__users">
    <hr class="nav__users--break">
    <a href="blank" class="nav__users--login">Login</a>
    <Button className="btn btn--signup">Sign Up</Button>
  </section>
</nav>

<style lang="scss">
  @import "../scss/global";

  .nav {
      display: flex;
      flex-direction: row;
      flex-wrap: wrap;
      margin-left: min(10rem, 5%);
      margin-right: min(10rem, 5%);
    &__img-box {
      margin-right: 1rem;
    }
    &__mobile-toggle{
      display: none;
      cursor: pointer;
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
      &--break{
        display: none;
        width: 15rem;
        margin-left: 0rem;
      }
      & > * {
        margin-right: 2rem;
      }
      & > a {
        color: $grayish-violet;
        font-weight: $fontweight-heavy;
      }
    }
  }

  @media (max-width: 375px){
    .nav{
      justify-content: space-between;
      &__mobile-toggle{
        display: inline-block;
      }
      &__main, &__users{
        position: absolute;
        display: none;
        flex-direction: column;
        margin: 0;
        left: 5%;
        right: 5%;
        width: auto;
        background-color: $dark-violet;
        & > *{
          color: white;
          margin-top: .25rem;
          margin-bottom: .25rem;
          margin-right: 0;
        }
      }
      &__main {
        top: 10vh;
        height: 8rem;
        text-align: center;
        padding-top: 1rem;
        border-top-left-radius: 1rem;
        border-top-right-radius: 1rem;
      }
      &__users{
        top: 25vh;
        padding-bottom: 1rem;
        border-bottom-left-radius: 1rem;
        border-bottom-right-radius: 1rem;
      align-items: center;
      &--break{
        display: block;
      }
      & > a {
        color: white;
        font-weight: $fontweight-heavy;
      }
      }
    }
  }
</style>
