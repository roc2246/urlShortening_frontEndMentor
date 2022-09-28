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
    <Button className="btn btn--CTA">Get Started</Button>
  </div>
    <img class="hero__image" src="images/illustration-working.svg" alt="" />
</section>

<style lang="scss">
  @import "../scss/global";
  .heading-primary {
    margin-bottom: 0;
    margin-top: 0;
    font-size: 4rem;
  }
  .paragraph-primary {
    color: $grayish-violet;
    font-weight: $fontweight-light;
    width: 25rem;
  }

  .hero {
    margin-top: 4rem;
    margin-bottom: 4rem;
    margin-left: 8rem;
    display: flex;
    flex-direction: row;
    flex-wrap: wrap-reverse;
    justify-content: center;

    &__text-box {
      display: flex;
      flex-direction: column;
      max-width: 28rem;
     
    }
    &__image {
      max-width: 100%;
      height: auto;
    }
  }

</style>
