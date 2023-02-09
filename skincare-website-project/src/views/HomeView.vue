<script setup></script>

<template>
    <div id="home-wrapper">
        <div>
            <img
                src="../assets/images/trinh-minh-th-h4cM5JQmxoQ-unsplash.jpg"
                alt="background"
                class="backgroundImg"
            />
        </div>
        <div id="items">
            <h3>New launch</h3>
            <h1>Sunscreen Stick SPF 50</h1>
            <p>
                Our SPF family is getting bigger! A lightweight sunscreen stick
                with broad spectrum, PA++++ and new-age UV filters to protect
                from UVA/UVB rays.
            </p>
            <input class="inpt" type="button" value="Buy Now" />
        </div>
    </div>

    <!-- image slide starts here -->

    <div class="home">
        <Carousel class="carousel" v-slot="{ currentSlide }">
            <Slide v-for="(slide, index) in carouselSlides" :key="index">
                <div v-show="currentSlide === index + 1" class="slide-products">
                    <!-- <img :src="require(`../assets/${slide}.jpg`)" alt="" /> -->

                    <img src="@/assets/img-2.jpg" />
                    <img src="@/assets/img-1.jpg" />

                    <img src="@/assets/img-3.jpg" />
                    <img src="@/assets/img-4.jpg" />
                </div>
            </Slide>
        </Carousel>
    </div>
</template>

<!-- vue js script for image slider -->

<script>
    import Carousel from '../components/Carousel.vue'
    import Slide from '../components/slide.vue'
    export default {
        name: 'Home',
        components: { Carousel, Slide },
        setup() {
            const carouselSlides = ['img-1', 'img-2', 'img-3', 'img-4']

            return { carouselSlides }
        }
    }
</script>
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

    .carousel {
        position: relative;
        max-height: 100vh;
        height: 100vh;
    }

    .slide-products img {
        margin-top: 80px;
        position: absolute;
        top: 0;
        left: 0;
        width: 700px;
        height: 100%;

        border: 2px solid black;

        object-fit: cover;
    }
</style>
