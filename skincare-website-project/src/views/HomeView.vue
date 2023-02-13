<script setup>
  
    import Slider from '../components/Slider.vue'
</script>

<template>
    <div id="home-wrapper">
        <div>
            <img
                src="../assets/trinh-minh-th-h4cM5JQmxoQ-unsplash.jpg"
                alt="background"
                class="backgroundImg"
            />
        </div>
        <div id="items">
            <h3>{{ text }}</h3>
            <h1>Serum ampoule</h1>
            <p>
                Our Serum family is getting bigger! A lightweight Serum ampoule
                with UV protection, new-age UV filters to protect from UVA/UVB
                rays.
            </p>
            <input
                class="inpt"
                type="button"
                value="Buy Now"
                @click="$router.push('/about')"
            />
        </div>
    </div>
    <Slider />
    <!-- image slide starts here -->


</template>

<!-- vue js script for image slider -->

<script></script>

<style scoped>
    .backgroundImg {
        height: 700px;
        width: 950px;
    }

    #home-wrapper {
        display: flex;
        justify-content: space-between;
        column-gap: 20px;
    }

    #items {
        display: flex;
        flex-direction: column;
        justify-content: center;
    }
    .inpt {
        width: 150px;
        padding: 7px;
        background-color: black;
        color: white;
    }
</style>
