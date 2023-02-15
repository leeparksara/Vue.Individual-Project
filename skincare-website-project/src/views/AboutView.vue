<script setup></script>

<template>
    <div class="about">
        <div class="card" style="width: 18rem">
            <img
                src="../assets/images/serum1.webp"
                class="card-img-top"
                alt="serum"
            />
            <div class="card-body">
                <h5 class="card-title">The ordinary Serum</h5>
                <p class="card-text">
                    Niacinamide 10% + Zinc 1% Oil Control Serum
                </p>

                <RouterLink class="btn btn-primary" to="/"
                    >Add To Cart</RouterLink
                >
            </div>
        </div>

        <div class="card" style="width: 18rem">
            <img
                src="../assets/images/serum2.webp"
                class="card-img-top"
                alt="serum"
            />
            <div class="card-body">
                <h5 class="card-title">The ordinary Serum</h5>
                <p class="card-text">
                    Niacinamide 10% + Zinc 1% Oil Control Serum
                </p>

                <RouterLink class="btn btn-primary" to="/"
                    >Add To Cart</RouterLink
                >
            </div>
        </div>

        <div class="card" style="width: 18rem">
            <img
                src="../assets/images/serum3.jpg"
                class="card-img-top"
                alt="serum"
            />
            <div class="card-body">
                <h5 class="card-title">The ordinary Serum</h5>
                <p class="card-text">
                    Niacinamide 10% + Zinc 1% Oil Control Serum
                </p>

                <RouterLink class="btn btn-primary" to="/"
                    >Add To Cart</RouterLink
                >
            </div>
        </div>
        <div class="card" style="width: 18rem">
            <img
                src="../assets/images/serum4.webp"
                class="card-img-top"
                alt="serum"
            />
            <div class="card-body">
                <h5 class="card-title">The ordinary Serum</h5>
                <p class="card-text">
                    Niacinamide 10% + Zinc 1% Oil Control Serum
                </p>

                <RouterLink class="btn btn-primary" to="/"
                    >Add To Cart</RouterLink
                >
            </div>
        </div>
    </div>
</template>

<style>
    @media (min-width: 1024px) {
        .about {
            min-height: 100vh;
            display: flex;
            align-items: center;
        }
    }
    .about {
        display: flex;
        justify-content: center;
        column-gap: 30px;
        background-color: rgb(222, 222, 222);
    }

    .btn-primary {
        background-color: rgb(32, 30, 30);
        width: 160px;
    }
</style>
