<template>
  <div id="homepage">
    <Hero />
    <AboutUs />
    <HowToApply />
    <FAQ />
    <FooterHome />
  </div>
</template>

<script>
  import Hero from "../components/Home/Hero.vue"
  import AboutUs from "../components/Home/AboutUs.vue"
  import HowToApply from "../components/Home/HowToApply.vue"
  import FAQ from "../components/Home/FAQ.vue"
  import FooterHome from "../components/Home/FooterHome.vue"

  export default {
    components: {
      Hero,
      AboutUs,
      HowToApply,
      FAQ,
      FooterHome
    }
  }
</script>