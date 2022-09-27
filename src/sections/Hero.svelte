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
  <img  src="images/illustration-working.svg" alt="" />
</div>
</section>

<style lang="scss">
  @import '../scss/global';
  .heading-primary{
    margin-bottom: 0;
    font-size: 6rem;
}
  .hero{
    display: flex;
    flex-direction: row;
    flex-wrap: wrap-reverse;
    margin-top: 2rem;
    justify-content: space-between;
    &__text-box{
      display: flex;
      flex-direction: column;
      max-width: 50rem;
    }
    &__image {
      // margin-left: 30rem;
      // overflow-x: hidden;
      &> img{
        max-width: 50rem;
        height: auto;
      }
    }
  }
</style>
