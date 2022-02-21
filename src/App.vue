<template>
  <Header />
  <main class="page-content">
    <Home />
  </main>
  <Footer />
</template> 

<script>
  import Header from "./components/Header.vue"
  import Footer from './components/Footer.vue'

  import Home from "./views/Home.vue"

  export default {
    components: {
      Header,
      Footer,
      Home
    }
  }
</script>

<style>
  /* DM Serif Display */
  @import url('https://fonts.googleapis.com/css2?family=DM+Serif+Display&display=swap');

  /* Rubik */
  @import url('https://fonts.googleapis.com/css2?family=Rubik:wght@300;400;500;700&display=swap');

  * {
    margin: 0;
    padding: 0;
  }
</style>