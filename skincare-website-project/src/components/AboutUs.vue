<template>
    <div>
        {{ text }}
        <img src="../assets/images/serum1.webp" alt="product-picture" />
    </div>
</template>

<script>
    export default {
        props: {
            type: string,
            required: true
        },
        data() {
            return {
                text: 'hello'
            }
        }
    }
</script>

<style></style>
