<template>
  <div class="signup">
    <div class="logo">
      <img alt="Vue logo" class="logo" src="../assets/logo.png" width="100" height="100" />
      <h2>Sign Up</h2>
    </div>

    <div class="register">
      <input type="text" v-model="name" placeholder="Enter Name">
      <input type="email" v-model="email" placeholder="Enter Email">
      <input type="password" v-model="password" placeholder="Enter Password">
      <button v-on:click="signUp">Sign Up</button>
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

<style scoped>
.signup {
  height: 100vh;
  display: flex;
  flex-direction: column;
  gap: 10px;
  justify-content: center;
  align-items: center;
}

.logo {
  display: flex;
  flex-direction: column;
  gap: 10px;
  justify-content: center;
  align-items: center;
}

.logo h2 {
  font-weight: 700;
  color: rgb(53, 103, 145);
}

.register input {
  width: 300px;
  height: 35px;
  display: flex;
  margin: 0 auto 20px auto;
  border: 1px solid rgb(53, 103, 145);
  border-radius: 5px;
  padding-left: 10px;
}

.register button {
  width: 300px;
  border: none;
  border-radius: 5px;
  background-color: rgb(53, 103, 145);
  color: #fff;
  font-size: 18px;
  padding: 8px 0;
  cursor: pointer;
}

.register button:hover {
  background-color: rgb(48, 116, 172);
}
</style>