<script setup>
    import { RouterLink, RouterView } from 'vue-router'
    import Fetch from './Fetch.vue'
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
                            <RouterLink class="nav-link" to="/NewView"
                                >About</RouterLink
                            >
                        </li>

                        <!-- Dropdown list for the products -->
                        <li class="nav-item dropdown">
                            <a
                                class="nav-link dropdown-toggle"
                                href="#"
                                role="button"
                                data-bs-toggle="dropdown"
                                aria-expanded="false"
                            >
                                Products
                            </a>

                            <ul class="dropdown-menu dropdown-menu-dark">
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
                            </ul>
                        </li>
                    </ul>
                </div>
            </div>
        </div>
    </nav>
    <RouterView />
</template>
<script></script>
