<template>
    <div>
      <h2>Sign Up</h2>
      <form @submit.prevent="signup">
        <input type="text" v-model="username" placeholder="Username" required>
        <input type="email" v-model="email" placeholder="Email" required>
        <input type="password" v-model="password" placeholder="Password" required>
        <button type="submit">Sign Up</button>
      </form>
    </div>
  </template>
  
  <script>
  import axios from 'axios';
  
  export default {
    data() {
      return {
        username: '',
        email: '',
        password: ''
      };
    },
    methods: {
      signup() {
        axios.post('http://your-api.com/signup', {
          username: this.username,
          email: this.email,
          password: this.password
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
  