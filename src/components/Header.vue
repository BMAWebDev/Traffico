<template>
  <header class="page-header">
    <div class="master-container">
      <div class="logo-container">
        <img src="@/assets/img/logo.svg" alt="">
      </div>
      <nav class="navbar display-desktop">
        <ul>
          <a href="#about-us-section"><li>About</li></a>
          <a href="#how-to-apply-section"><li>How To</li></a>
          <a href="#faq-section"><li>FAQS</li></a>
          <a href="#footer-home-section"><li class="contact-us-btn">Contact Us</li></a>
        </ul>
      </nav>
      <div @click="toggleMenu" class='burger-menu display-mobile' :class="{ 'active-menu': mobileMenuActive }">
        <i class="fa-solid fa-bars mobile-menu-toggle-icon"></i>
        
        <nav class="navbar menu-mobile d-none"> 
          <ul>
            <a href="#about-us-section"><li>About</li></a>
            <a href="#how-to-apply-section"><li>How To</li></a>
            <a href="#faq-section"><li>FAQS</li></a>
            <a href="#footer-home-section"><li class="contact-us-btn">Contact Us</li></a>
          </ul>
        </nav>
      </div>
    </div>
  </header>
</template>

<script>
  import '@/assets/css/header.css'

  export default {
    data() {
      return {
        mobileMenuActive: false
      }
    },
    methods: {
      toggleMenu(){
        this.mobileMenuActive = !this.mobileMenuActive
      }
    },
  }
</script>