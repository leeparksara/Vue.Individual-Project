<template>
    <div class="carousel">
        <slot :currentSlide="currentSlide" />
    </div>
</template>

<script>
    // we need to import ref to be able to use it inside the setup option
    import { ref } from 'vue'

    export default {
        setup() {
            const currentSlide = ref(2)
            return { currentSlide } //Return the data value
        }
    }
</script>

<style></style>
