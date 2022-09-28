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
  <div class="hero__image">
    <img src="images/illustration-working.svg" alt="" />
  </div>
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
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    margin-left: 10rem;
    &__text-box {
      display: flex;
      flex-direction: column;
    }
    &__image {
      max-width: 100%;
    }
  }

@media(max-width: 375px){
  .hero{
    flex-wrap: wrap-reverse;

  }
}
</style>
