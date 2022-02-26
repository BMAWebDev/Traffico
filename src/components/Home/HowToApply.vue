<template>
  <section id="how-to-apply-section" class="how-to-apply">
    <div class="master-container">
      <div class="disk left-content">
        <img class="how-to-apply-call animate initialAnimPos" src="@/assets/img/how-to-apply-call.svg" alt="">
      </div>
      <div class="disk right-content">
        <div class="text-container">
          <h2 class="section-title">How to apply</h2>
          <p class="section-description">
            When applying for a traffic permit, there are certain requirements that you must meet that are included in the examination: requirements for professional knowledge, solid establishment, good reputation and financial resources. Important to remember is to confirm your application for a traffic permit by the company's company signer or CEO.
          </p>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
  import '@/assets/css/how-to-apply.css'

  export default {
    created() {
      window.addEventListener('scroll', this.animate);
    },
    destroyed() {
      window.removeEventListener('scroll', this.animate);
    },
    methods: {
      animate(){
        const howToApplyCall = document.querySelector('.how-to-apply-call.animate');
        if(window.scrollY >= howToApplyCall.offsetTop - howToApplyCall.height){
          howToApplyCall.classList.remove('initialAnimPos');
        }
        else{
          howToApplyCall.classList.add('initialAnimPos');
        }
      }
    },
  }
</script>