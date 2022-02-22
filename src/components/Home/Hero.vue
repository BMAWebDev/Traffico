<template>
  <section class="hero">
    <div class="master-container">
      <div class="text-container">
        <h1 class="company-description">Your awesome traffic permit consultant.</h1>
        <a href="#">
          <button class="get-started">Get started <img src="@/assets/img/arrow-right.svg" alt=""></button>
        </a>
      </div>
      <img class="car" src="@/assets/img/car.svg" alt="">
    </div>
  </section>
</template>

<script>
  import '@/assets/css/hero.css'
  import gsap from 'gsap'

  export default {
    mounted() {
      gsap.from('.car', {
        duration: 3, 
        x: -750
      })
    },
  }
</script>