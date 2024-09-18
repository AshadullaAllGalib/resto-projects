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
            <button>Login</button>

            <div class="user-login">
                <p>Not Yet Registered</p>
                <router-link to="/sign-up">Sign-Up</router-link>
            </div>

        </div>
    </div>
</template>

<script>
export default {
    name: 'Login'

}
</script>

<style scoped></style>