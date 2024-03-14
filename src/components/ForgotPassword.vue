<template>
    <div>
      <h2>Forgot Password</h2>
      <form @submit.prevent="forgotPassword">
        <input type="email" v-model="email" placeholder="Email" required>
        <button type="submit">Submit</button>
      </form>
    </div>
  </template>
  
  <script>
  import axios from 'axios';
  
  export default {
    data() {
      return {
        email: ''
      };
    },
    methods: {
      forgotPassword() {
        axios.post('http://your-api.com/forgot-password', {
          email: this.email
        })
        .then(response => {
          console.log(response.data);
        })
        .catch(error => {
          console.error(error);
        });
      }
    }
  }
  </script>
  