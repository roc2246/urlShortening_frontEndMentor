<script>
  export let image;
  export let heading;
  export let paragraph;
</script>

<div class="blurb">
  <div class="blurb__img-box">
    <img src={image} alt={heading} />
  </div>
  <h1 class="heading-tertiary">{heading}</h1>
  <p class="paragraph-tertiary">{paragraph}</p>
</div>

<style lang="scss">
  @import '../scss/global';
  .blurb {
    border: solid;
    border-radius: 0.5rem;
    width: 16rem;
    height: 12rem;
    padding: 1rem;
    &__img-box {
      position: absolute;
      margin-top: -3.5rem;
      border-radius: 50%;
      padding: .75rem;
      background-color: $dark-violet;
    }
    &:nth-child(2) {
      margin-top: 2rem;
    }
    &:nth-child(3) {
      margin-top: 4rem;
    }
  }
</style>
