<template>
  <section class="about-us">
    <div class="master-container">
      <div class="disk left-content">
        <div class="text-container">
          <h2 class="section-title">About us</h2>
          <p class="section-description">
            The occupational traffic permit is one of the most important things in the company when carrying out freight transport. In fact, it is a prerequisite for doing business traffic at all. 
          </p>
        </div>
        <div class="question-container">
          <p class="question-text">
            How do you do when you need to obtain a commercial traffic permit for freight transport to your business?
          </p>
        </div>
      </div>
      <div class="disk right-content">
        <img class="about-us-delivery" src="@/assets/img/about-us-delivery.svg" alt="">
      </div>
    </div>
  </section>
</template>

<script>
  import '@/assets/css/about-us.css'
  import gsap from 'gsap'

  export default {
    mounted() {
      gsap.from('.about-us-delivery', {
        duration: 3, 
        x: 1500
      })
    },
  }
</script>