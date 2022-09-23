<script>
  import Blurb from "../components/Blurb.svelte";

  const blurbs = [
    {
      img: 'images/icon-brand-recognition.svg',  
      title: "Brand Recognition",
      text: `Boost your brand recognition with each click. Generic links don’t 
                mean a thing. Branded links help instil confidence in your content.`,
    },
    {
      img: 'images/icon-detailed-records.svg',  
      title: "Detailed Records",
      text: `Gain insights into who is clicking your links. Knowing when and where 
  people engage with your content helps inform better decisions.`,
    },
    {
      img: 'images/icon-fully-customizable.svg',  
      title: "Fully Customizable",
      text: `  Improve brand awareness and content discoverability through customizable 
  links, supercharging audience engagement.`,
    },
  ];

</script>

<section class="blurb-container">
  <div class="blurb-container__text-box">
    <h2 class="heading-secondary">Advanced Statistics</h2>
    <p class="paragraph-secondary">
      Track how your links are performing across the web with our advanced
      statistics dashboard.
    </p>
  </div>
  <div class="blurb-container__blurbs">
    {#each blurbs as blurb}
    <Blurb image={blurb.img} heading={blurb.title} paragraph={blurb.text}/>
    {/each}
  </div>
</section>
