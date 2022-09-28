<script>
    import Button from "../components/Button.svelte";
</script>

<section class="CTA">
    <h2 class="heading-secondary--CTA">Boost your links today</h2>
    <Button className="btn btn--CTA">Get Started</Button>
</section>

<style lang="scss">
      @import "../scss/global";
h2{
    color: white;
    white-space: nowrap;
}   
    .CTA{
        background-image: url("/images/bg-boost-desktop.svg");
    background-color: $very-dark-violet;
        display: flex;
        flex-direction: column;
        align-items: center;
        padding-left: 10rem;
        padding-right: 10rem;
    }
</style>