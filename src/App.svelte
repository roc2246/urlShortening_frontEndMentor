<script>
  import Navigation from "./sections/Navigation.svelte";
  import Hero from "./sections/Hero.svelte";
  import Form from "./sections/Form.svelte"
  import BlurbContainer from "./sections/BlurbContainer.svelte";
  import CTA from "./sections/CTA.svelte"
  import Footer from "./sections/Footer.svelte"
</script>

<main>
  <Navigation navMode="nav--desktop" />
  <Hero />
  <Form />
  <BlurbContainer />
  <CTA />
  <Footer />
</main>

<style>
</style>
