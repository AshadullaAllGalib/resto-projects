<template>
  <div class="signup">
    <div class="logo">
      <img alt="Vue logo" class="logo" src="../assets/logo.png" width="110" height="100" />
      <h2>Sign Up</h2>
    </div>

    <div class="register">
      <input type="text" v-model="name" placeholder="Enter Name">
      <input type="email" v-model="email" placeholder="Enter Email">
      <input type="password" v-model="password" placeholder="Enter Password">
      <button v-on:click="signUp">Sign Up</button>

      <div class="user-login">
        <p>Already Registered</p>
        <router-link to="/login">Login</router-link>
      </div>

    </div>
  </div>


</template>

<script>

import axios from 'axios';

export default {
  name: 'SignUp',
  data() {
    return {
      name: '',
      email: '',
      password: ''
    }
  },
  methods: {
    async signUp() {
      let result = await axios.post("http://localhost:3000/user", {
        email: this.email,
        password: this.password,
        name: this.name
      });

      console.warn(result);

      if (result.status = 201) {
        localStorage.setItem("user-info", JSON.stringify(result.data))
        this.$router.push({ name: "Home" })
      }
    }
  },

  mounted() {
    let user = localStorage.getItem('user-info');
    if (user) {
      this.$router.push({ name: "Home" })
    }
  },
}
</script>

<style scoped></style>