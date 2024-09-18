<template>
    <div class="signup login">
        <div class="logo">
            <img alt="Vue logo" class="logo" src="../assets/login-logo.png" width="110"
                height="100" />
            <h2>Login</h2>
        </div>

        <div class="register">
            <!-- <input type="text" v-model="name" placeholder="Enter Name"> -->
            <input type="email" v-model="email" placeholder="Enter Email">
            <input type="password" v-model="password" placeholder="Enter Password">
            <button v-on:click="login">Login</button>

            <div class="user-login">
                <p>Not Yet Registered</p>
                <router-link to="/sign-up">Sign-Up</router-link>
            </div>

        </div>
    </div>
</template>

<script>
import axios from 'axios';
export default {
    name: 'Login',

    data() {
        return {
            email: '',
            password: ''
        }
    },

    methods: {
        async login() {
            let result = await axios.get(
                `http://localhost:3000/user?email=${this.email}&${this.password}`
            )
            console.warn(result);

            if (result.status = 200 && result.data.length > 0) {
                localStorage.setItem("user-info", JSON.stringify(result.data[0]))
                this.$router.push({ name: "Home" })
            }

        }
    },

    mounted() {
        let user = localStorage.getItem('user-info');
        if (user) {
            this.$router.push({ name: "Home" })
        }
    }

}
</script>

<style scoped></style>