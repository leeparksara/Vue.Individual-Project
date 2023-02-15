<template>
    <div>
        <h3 style="white-space: pre-line">
            {{ aboutText }}
        </h3>
        <img src="../assets/images/about.jpg" alt="product-picture" />
    </div>
</template>

<script>
    export default {
        data() {
            return {
                aboutText: ` Our natural and organic skin care and organic \n beauty products carry the story  of women and men empowered by your purchase. \n
                      Our products are good for you and good for survivors of human   trafficking - a win-win solution`
            }
        }
    }
</script>

<style scoped>
    img {
        width: 60%;
        height: 100%;
    }
    div {
        display: flex;
        flex-direction: row-reverse;
        justify-content: center;
        align-items: center;
        column-gap: 2%;
        margin: 2%;
        margin-top: 10%;
    }
    h3 {
        font-size: medium;
    }
</style>
