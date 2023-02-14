<template>
    <!-- Image slider starts here  -->
    <div>
        <!-- Wrapping the div and img tag with transition tag to animate the images-->
        <transition-group name="fade" tag="div" class="slideImage">
            <!-- Use v-for eirective to loop through the array of images with their index-->
            <div v-for="i in [currentIndex]" :key="i">
                <img :src="currentImg" class="slides" />
            </div>
        </transition-group>
    </div>
</template>
<script>
    // Slider script starts here
    export default {
        name: 'SlideShow',
        data() {
            return {
                images: [
                    'https://images.unsplash.com/photo-1614859475299-814a09cd2e79?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1470&q=80',
                    'https://images.unsplash.com/photo-1575249142951-35b95b9bb5b7?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1470&q=80',
                    'https://images.unsplash.com/photo-1576426863848-c21f53c60b19?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1470&q=80',
                    'https://images.pexels.com/photos/8100816/pexels-photo-8100816.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=2'
                ],
                timer: null,
                currentIndex: 0
            }
        },
        // mounted function will render the images auto
        mounted: function () {
            this.startSlide()
        },
        methods: {
            startSlide: function () {
                this.timer = setInterval(this.nextSlide, 3000)
            },
            nextSlide: function () {
                this.currentIndex += 1
            },
            prevSlide: function () {
                this.currentIndex -= 1
            }
        },
        computed: {
            currentImg: function () {
                return this.images[
                    Math.abs(this.currentIndex) % this.images.length
                ]
            }
        }
    }
</script>
<style scoped>
    .fade-enter-active,
    .fade-leave-active {
        transition: all 1s ease;
        overflow: hidden;
        visibility: visible;
        position: absolute;
        width: 100%;
        opacity: 1;
    }
    .fade-enter,
    .fade-leave-to {
        visibility: hidden;
        width: 100%;
        opacity: 0;
    }

    /* Position the "next button" to the right */
    /* On hover, add a black background color with a little bit see-through */

    .slides {
        width: 1000px;
        height: 600px;
        margin: 60px;

        margin-left: 16%;
    }
    .slideImage {
        justify-content: center;
    }
</style>
