<script>
  import Button from "../components/Button.svelte";
</script>

<section class="hero">
  <div class="hero__text-box">
    <h1 class="heading-primary">More than just shorter links</h1>
    <p class="paragraph-primary">
      Build your brand's recognition and get detailed insights on how your links
      are performing.
    </p>
    <Button>Get Started</Button>
  </div>

    <img class="hero__image" src="images/illustration-working.svg" alt="" />
</section>

<style lang="scss">
  .hero{
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    &__text-box{
      display: flex;
      flex-direction: column;
    }
    &__image{
      max-width: 20rem;
      height: auto;
    }
  }
</style>
