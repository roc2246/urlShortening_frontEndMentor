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
  }

  .hero {
    margin-top: 4rem;
    margin-bottom: 4rem;
    margin-left: min(10rem, 5%);
      margin-right: min(10rem, 5%);
    display: flex;
    flex-direction: row;
    flex-wrap: wrap-reverse;
    justify-content: space-between;

    &__text-box {
      display: flex;
      flex-direction: column;
      max-width: 28rem;
      width: 100%;
     
    }
    &__image {
      max-width: 100%;
      height: auto;
    }
  }

  @media (max-width: 375px) {
    .heading-primary {
    margin-bottom: 0;
    margin-top: 0;
    font-size: 3rem;
  }
  .hero{
    &__text-box{
      text-align: center;
      align-items: center;
    }
   
  }
  }

</style>
