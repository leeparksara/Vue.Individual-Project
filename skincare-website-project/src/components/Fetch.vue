<template>
    <!-- List of item displays when the form is submitted -->
    <div>
        <form @submit.prevent="SearchProduct">
            <input type="text" v-model="searchTerm" />
            <button type="submit">Search</button>
        </form>

        <ul>
            <li v-for="item in items" :key="item">
                <img :src="path" />
                <h4>{{ item.product }}</h4>
                <h5>{{ item.price }}</h5>
                {{ item.img }}
            </li>
        </ul>
    </div>
</template>

<script>
    import axios from 'axios'

    export default {
        data() {
            return {
                searchTerm: '',
                items: []
            }
        },
        methods: {
            SearchProduct() {
                axios
                    .get(`/data.json${this.searchTerm}`)
                    .then((response) => {
                        this.items = response.data
                    })
                    .catch((error) => {
                        console.error(error)
                    })
            }
        }
    }
</script>

<style scoped>
    ul {
        background-color: rgb(231, 222, 240);
    }
</style>
