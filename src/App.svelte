<script>
  import Navigation from "./sections/Navigation.svelte";
  import Hero from "./sections/Hero.svelte";
  import Form from "./sections/Form.svelte"
  import BlurbContainer from "./sections/BlurbContainer.svelte";
  import CTA from "./sections/CTA.svelte"
  import Footer from "./sections/Footer.svelte"
</script>

<Navigation />
<main>
  <Hero />
  <Form />
  <BlurbContainer />
  <CTA />
</main>
<Footer />

<style>
  main{
    /* max-width: 98rem; */
    margin-left: auto;
    margin-right: auto;
  }
</style>
