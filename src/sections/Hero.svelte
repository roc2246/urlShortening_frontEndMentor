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
<div class="hero__image">
  <img  src="images/illustration-working.svg" alt="" />
</div>
</section>

<style lang="scss">
  @import '../scss/global';
  .hero{
    display: flex;
    flex-direction: row;
    margin-top: 2rem;
    &__text-box{
      display: flex;
      flex-direction: column;
      max-width: 50rem;
    }
    &__image {
      margin-left: 10rem;
      // overflow-x: hidden;
      &> img{
        max-width: 50rem;
        height: auto;
      }
    }
  }
</style>
