<template>
    <Header />
    <div>
        <h1>Hello User, Welcome on Add restaurant page</h1>
    </div>
</template>

<script>
import Header from './Header.vue';
export default {
    name: "Add",
    components: {
        Header
    },

    mounted() {
        let user = localStorage.getItem('user-info');
        if (!user) {
            this.$router.push({ name: "SignUp" })
        }
    },

}
</script>

<style scoped></style>