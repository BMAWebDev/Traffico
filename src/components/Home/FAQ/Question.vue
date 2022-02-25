<template>
  <li class="question"  :id="'question-' + index">
    <div class="question-container">
      <h3>{{ question.title }} <span @click="toggleResponse(index)" class="toggleQuestion">+</span></h3>
    </div>
    <div class="response-container d-none">
      <p class="response">{{ question.Message }}</p>
    </div>
  </li>
</template>

<script>
  export default {
    props: {
      question: Object,
      index: Number
    },
    methods: {
      toggleResponse(index){
        const currentQuestion = document.querySelectorAll('.question')[index];

        document.querySelectorAll('.question').forEach((question, ndx) => {
          if(ndx == index){
            let currentResContainer = currentQuestion.querySelector('.response-container');
            if(currentResContainer.classList.contains('d-none'))
              currentQuestion.querySelector('.toggleQuestion').textContent = '-';
            else
              currentQuestion.querySelector('.toggleQuestion').textContent = '+';

            currentResContainer.classList.toggle('d-none');
          }
          else if(!question.querySelector('.response-container').classList.contains('d-none')){
            question.querySelector('.response-container').classList.add('d-none')
            question.querySelector('.toggleQuestion').textContent = '+';
          }
        });
      }
    }
  }
</script>