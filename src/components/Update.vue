<template>
    <Header />
    <div class="title">
        <h1>Hello User, Welcome on Update restaurant page</h1>
    </div>

    <div class="register">
        <form>
            <input type="text" name="name" placeholder="Enter Name" v-model="restaurant.name">
            <input type="text" name="address" placeholder="Enter address"
                v-model="restaurant.address">
            <input type="text" name="contact" placeholder="Enter contact"
                v-model="restaurant.contact">
            <button type="button" v-on:click="updateRestaurant">Update Restaurant</button>
        </form>
    </div>
</template>

<script>
import Header from './Header.vue';
import axios from 'axios';
export default {
    name: "Update",
    components: {
        Header
    },

    data() {
        return {
            restaurant: {
                name: '',
                address: '',
                contact: ''
            }
        }
    },

    methods: {
        async updateRestaurant() {
            console.warn(this.restaurant)
            const result = await axios.put("http://localhost:3000/restaurant/" + this.$route.params.id, {
                name: this.restaurant.name,
                address: this.restaurant.address,
                contact: this.restaurant.contact
            });

            if (result.status == 200) {
                this.$router.push({ name: 'Home' })
            }
            // console.warn("result", result)

        }
    },

    async mounted() {
        let user = localStorage.getItem('user-info');
        if (!user) {
            this.$router.push({ name: 'SignUp' })
        }
        const result = await axios.get('http://localhost:3000/restaurant/' + this.$route.params.id)
        // console.warn(result)
        // console.warn(this.$route.params.id)
        this.restaurant = result.data
    },

}
</script>

<style scoped></style>