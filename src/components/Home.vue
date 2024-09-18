<template>
    <div>
        <h1>Hello User, Welcome on Home page</h1>
    </div>
</template>

<script>
export default {
    name: "Home",

    mounted() {
        let user = localStorage.getItem('user-info');
        if (!user) {
            this.$router.push({ name: "SignUp" })
        }
    },

}
</script>

<style scoped></style>