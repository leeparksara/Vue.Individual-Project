<template>
    <div class="carousel">
        <div class="slides">
            <transition-group name="slide" tag="div">
                <div
                    v-for="(slide, index) in slides"
                    :key="index"
                    class="slide"
                >
                    <img :src="slide.src" alt="Slide product" />
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
                        src: 'https://images.unsplash.com/photo-1586212653598-40f9046fe5e3?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1470&q=80'
                    },
                    {
                        src: 'https://images.unsplash.com/photo-1575249142951-35b95b9bb5b7?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1470&q=80'
                    },
                    {
                        src: 'https://images.unsplash.com/photo-1576426863848-c21f53c60b19?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1470&q=80'
                    }
                ],
                currentIndex: 0
            }
        },
        methods: {
            prevSlide() {
                this.currentIndex === this.currentIndex--
            },
            nextSlide() {
                this.currentIndex === this.currentIndex++
            }
        }
    }
</script>

<style>
    .carousel {
        margin-top: 80px;
        margin-bottom: 80px;
        display: flex;
        flex-direction: column;
        align-items: center;
    }

    .slides {
        width: 900px;
        height: 600px;
        overflow: hidden;
        position: relative;
    }

    .slide {
        position: absolute;
        top: 0;
        left: 0;
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
    .nav button {
        background-color: rgb(203, 199, 199);
        color: black;
    }

    .slide-enter-active {
        transition: all 0.3s;
    }
    .slide-leave-active {
        transition: all 0.3s;
    }

    .slide-enter {
        transform: translateX(-100%);
    }
    .slide-leave-to {
        transform: translateX(-100%);
    }
</style>
