<template>
    <div class="carousel">
        <div class="slides">
            <transition-group name="slide" tag="div">
                <div
                    v-for="(slide, index) in slides"
                    :key="index"
                    class="slide"
                >
                    <img :src="slide.src" alt="Slide Image" />
                </div>
            </transition-group>
        </div>
        <div class="nav">
            <button @click="prevSlide">Prev</button>
            <button @click="nextSlide">Next</button>
        </div>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                slides: [
                    {
                        src: 'https://images.unsplash.com/photo-1575249142951-35b95b9bb5b7?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1470&q=80'
                    },
                    {
                        src: 'https://images.unsplash.com/photo-1586212653598-40f9046fe5e3?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1470&q=80'
                    },
                    {
                        src: 'https://images.unsplash.com/photo-1586212653598-40f9046fe5e3?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1470&q=80'
                    }
                ],
                currentIndex: 0
            }
        },
        methods: {
            prevSlide() {
                this.currentIndex =
                    this.currentIndex === 0
                        ? this.slides.length - 1
                        : this.currentIndex - 1
            },
            nextSlide() {
                this.currentIndex =
                    this.currentIndex === this.slides.length - 1
                        ? 0
                        : this.currentIndex + 1
            }
        }
    }
</script>

<style>
    .carousel {
        display: flex;
        flex-direction: column;
        align-items: center;

        margin-top: 50px;
    }

    .slides {
        width: 900px;
        height: 600px;
        overflow: hidden;
        position: relative;
    }

    .slide {
        width: 100%;
        height: 100%;
    }

    .slide img {
        width: 100%;
        height: 100%;
        object-fit: cover;
    }

    .nav {
        display: flex;
        justify-content: space-between;
        width: 300px;
        margin-top: 20px;
    }

    .slide-enter-active,
    .slide-leave-active {
        transition: all 0.3s;
    }

    .slide-enter,
    .slide-leave-to {
        transform: translateX(-100%);
    }
</style>
