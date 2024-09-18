<template>
    <div class="nav">
        <router-link to="/">Home</router-link>
        <router-link to="/add">Add Restaurant</router-link>
        <router-link to="/update">Remove Restaurant</router-link>
        <a v-on:click="logout" href="#">Logout</a>
    </div>
</template>

<script>
export default {
    name: 'Header',
    methods: {
        logout() {
            localStorage.clear();
            this.$router.push({ name: 'Login' })
        }
    }
}
</script>

<style scoped>
.nav {
    background-color: rgb(50, 114, 170);
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 40px;
}

.nav a {
    text-decoration: none;
    color: #fff;
    font-size: 18px;
    padding: 10px;
}

.nav a:hover {
    background-color: rgb(4, 46, 83);
}
</style>