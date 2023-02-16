<template>
    <!--  Hero image and hero text -->
    <div id="home-wrapper">
        <div>
            <img
                src="../assets/images/hero.avif"
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

            <!-- Link that takes user to another page  -->
            <input
                class="inpt"
                type="button"
                value="Buy Now"
                @click="$router.push('/about')"
            />
        </div>
    </div>

    <!-- Slider component starts here -->

    <div class="sli">
        <SlideShow />
    </div>
</template>

<!-- vue js script for image slider -->

<script>
    import SlideShow from '../components/SlideShow.vue'

    export default {
        name: 'slider-app',
        components: { SlideShow },
        data() {
            return {
                text: 'New Collection'
            }
        }
    }
</script>

<style scoped>
    .backgroundImg {
        height: 650px;
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
    .sli {
        position: sticky;
    }
</style>
