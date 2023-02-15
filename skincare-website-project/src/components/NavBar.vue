<script setup>
    import { RouterLink, RouterView } from 'vue-router'

    import UserLogIn from './UserLogIn.vue'
</script>

<template>
    <nav class="navbar navbar-dark bg-dark fixed-top">
        <div class="container-fluid">
            <!--search bar-->
            <Fetch />
            <!-- Brand logo -->
            <RouterLink class="navbar-brand" to="/">Hella Co.</RouterLink>

            <button
                class="navbar-toggler"
                type="button"
                data-bs-toggle="offcanvas"
                data-bs-target="#offcanvasDarkNavbar"
                aria-controls="offcanvasDarkNavbar"
            >
                <span class="navbar-toggler-icon"></span>
            </button>
            <div
                class="offcanvas offcanvas-end text-bg-dark"
                tabindex="-1"
                id="offcanvasDarkNavbar"
                aria-labelledby="offcanvasDarkNavbarLabel"
            >
                <div class="offcanvas-header">
                    <h5 class="offcanvas-title" id="offcanvasDarkNavbarLabel">
                        Hella Co.
                    </h5>

                    <button
                        type="button"
                        class="btn-close btn-close-white"
                        data-bs-dismiss="offcanvas"
                        aria-label="Close"
                    ></button>
                </div>

                <UserLogIn />

                <div class="offcanvas-body">
                    <ul class="navbar-nav justify-content-end flex-grow-1 pe-3">
                        <li class="nav-item">
                            <RouterLink
                                class="nav-link active"
                                aria-current="page"
                                to="/"
                                >Home</RouterLink
                            >
                        </li>
                        <li class="nav-item">
                            <RouterLink class="nav-link" to="/us"
                                >About</RouterLink
                            >
                        </li>

                        <!-- Dropdown list for the products -->
                        <li class="nav-item dropdown">
                            <a
                                @click="SearchProduct"
                                class="nav-link dropdown-toggle"
                                href="#"
                                role="button"
                                data-bs-toggle="dropdown"
                                aria-expanded="false"
                            >
                                Product
                            </a>

                            <table class="product-list">
                                <thead>
                                    <tr>
                                        <th>name</th>
                                        <th>price</th>
                                        <th>Quantity</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr v-for="item in items" :key="item">
                                        <td>
                                            {{ item.product }}
                                        </td>
                                        <td>
                                            {{ item.price }}
                                        </td>
                                        <td>
                                            {{ item.quantity }}
                                        </td>
                                    </tr>
                                </tbody>
                            </table>

                            <!--   <ul class="dropdown-menu dropdown-menu-dark">
                                <li>
                                    <RouterLink class="dropdown-item" to="/"
                                        >Dry Skin</RouterLink
                                    >
                                </li>
                                <li>
                                    <a class="dropdown-item" href="#"
                                        >Oily Skin</a
                                    >
                                </li>
                                <li>
                                    <hr class="dropdown-divider" />
                                </li>
                                <li>
                                    <a class="dropdown-item" href="#"
                                        >Body Care
                                    </a>
                                </li>



                     </ul> -->
                        </li>
                    </ul>
                </div>
            </div>
        </div>
    </nav>
    <RouterView />
</template>
<script>
    import axios from 'axios'

    export default {
        data() {
            return {
                items: []
            }
        },
        methods: {
            SearchProduct() {
                axios
                    .get(`/data.json`)
                    .then((response) => {
                        this.items = response.data
                    })
                    .catch((error) => {
                        console.error(error)
                    })
            }
        }
    }
</script>

<style scoped>
    .product-list {
        background-color: rgb(223, 229, 235);
        visibility: visible;
    }
    tr {
        display: flex;
        justify-content: space-evenly;
        column-gap: 30px;
        row-gap: 20px;
        margin: 10px;
        color: rgb(31, 30, 30);
    }
    th {
        color: rgb(34, 113, 174);
    }
</style>
