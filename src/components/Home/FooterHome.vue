<template>
  <section id="footer-home-section" class="footer-home">
    <div class="master-container">
      <div class="background"></div>
      <div class="row1">
        <div class="car-scene">
          <img class="cloud-1" src="@/assets/img/footer-home-cloud-1.svg" alt="">
          <img class="car animate initialAnimPos" src="@/assets/img/footer-home-car.svg" alt="">
          <img class="cloud-2" src="@/assets/img/footer-home-cloud-2.svg" alt="">
        </div>
        <div class="text-container">
          <p class="footer-description">
            We provide traffic management consultants so you get started quickly, contact us for a quote today!
          </p>
        </div>
        <div class="form-container">
          <Form />
        </div>
      </div>
      <div class="row2 footer-navigation">
        <div class="logo-container">
          <img src="@/assets/img/logo.svg" alt="">
        </div>
        <ul class="navigation-container">
          <a href="#about-us-section"><li>About</li></a>
          <a href="#how-to-apply-section"><li>How to</li></a>
          <a href="#faq-section"><li>FAQS</li></a>
        </ul>
      </div>
    </div>
  </section>
</template>

<script>
  import '@/assets/css/footer-home.css'
  import Form from './FooterHome/Form.vue'

  export default {
    components: {
      Form
    },
    created() {
      window.addEventListener('scroll', this.animate);
    },
    destroyed() {
      window.removeEventListener('scroll', this.animate);
    },
    methods: {
      animate(){
        const footerCar = document.querySelector('.footer-home').querySelector('.car.animate');
        if(window.scrollY >= footerCar.getBoundingClientRect().top - document.body.getBoundingClientRect().top - 3 * footerCar.height){
          footerCar.classList.remove('initialAnimPos');
        }
        else{
          footerCar.classList.add('initialAnimPos');
        }
      }
    },
  }
</script>