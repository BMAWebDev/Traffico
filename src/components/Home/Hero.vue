<template>
  <section class="hero">
    <div class="master-container">
      <div class="text-container">
        <h1 class="company-description">Your awesome traffic permit consultant.</h1>
        <a href="#">
          <button class="get-started">Get started <img src="@/assets/img/arrow-right.svg" alt=""></button>
        </a>
      </div>
      <img class="car animate initialAnimPos" src="@/assets/img/car.svg" alt="">
    </div>
  </section>
</template>

<script>
  import '@/assets/css/hero.css'

  export default {
    created() {
      window.addEventListener('scroll', this.animate);
    },
    destroyed() {
      window.removeEventListener('scroll', this.animate);
    },
    methods: {
      // function to detect element position on scroll and toggle the animation process
      animate(){
        const car = document.querySelector('.car.animate');
        if(window.scrollY >= car.offsetTop - car.height){
          car.classList.remove('initialAnimPos');
        }
        else{
          car.classList.add('initialAnimPos');
        }
      }
    },
  }
</script>