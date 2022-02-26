<template>
  <form @submit="validateForm" name="get-started-form" id="get-started-form">
    <div class="form-group">
      <label for="name">Name</label>
      <input type="text" name="name" id="name" class="form-input" placeholder="Your name">
      <span id="nameErr" class="error"></span>
    </div>
    <div class="form-group">
      <label for="email">Email address</label>
      <input type="email" name="email" id="email" class="form-input" placeholder="Your email address">
      <span id="emailErr" class="error"></span>
    </div>
    <button class="submit-btn" type="submit">Get started <img src="@/assets/img/arrow-right.svg" alt="arrow-right"></button>
  </form>
</template>

<script>
  export default {
    methods: {
      isEmailValid(email){
        const regex = /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;

        if (email.match(regex)) return true;

        return false;
      },
      validateForm(e){
        const form = document.forms['get-started-form'];
        const name = form['name'].value;
        const email = form['email'].value;
        
        let errors = false;

        if(!name){
          document.querySelector('#nameErr').textContent = 'Name is mandatory'
          errors = true
        }
        else{
          document.querySelector('#nameErr').textContent = ''
        }
        
        if(!email || !this.isEmailValid(email)){
          document.querySelector('#emailErr').textContent = 'Email is not valid'
          errors = true
        }
        else{
          document.querySelector('#emailErr').textContent = ''
        }

        if(errors){
          e.preventDefault();
          return false;
        }

        return true;
      }
    },
  }
</script>