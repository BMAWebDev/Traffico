<template>
  <section class="faq">
    <div class="master-container">
      <div class="colored-background"></div>
      <div class="section-content">
        <div class="section-description">
          <div class="text-container">
            <h2 class="section-title">FAQ</h2>
            <h2 class="questions-title">Questions and Answers on Professional Traffic Permits:</h2>
          </div>
          <div class="delivery-img-container">
            <img src="@/assets/img/faq-delivery.svg" alt="">
          </div>
        </div>
        <ul class="questions-container">
          <Question v-for="(question, index) in questionsToShow" :key="index" :question="question" :index="index" />
        </ul>
        <button v-if="currentQuestionsAvailable < questions.length" @click="loadMore" class="load-more-btn">Load more <span>+</span></button>
      </div>
    </div>
  </section>
</template>

<script>
  import '@/assets/css/faq.css'
  import axios from 'axios'
  import Question from './FAQ/Question.vue'

  export default {
    data() {
      return {
        questions: [],
        questionsPerLoad: 5,
        questionsToShow: [],
        currentQuestionsAvailable: 0,
      }
    },
    components: {
      Question
    },
    methods: {      
      loadMore(){
        this.currentQuestionsAvailable += this.questionsPerLoad
        this.questionsToShow = this.questions.slice(0, this.currentQuestionsAvailable)
      }
    },
    async mounted() {
      const response = await axios.get('https://hook.integromat.com/syyhp9cj3ikey0hhi089wb3xjdy5d9s6')
      this.questions = response.data.response;
      this.loadMore()
    },
  }
</script>