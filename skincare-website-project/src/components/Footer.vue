<template>
    <!-- Footer -->
    <footer class="text-center text-white">
        <!-- Copyright -->
        <div class="text-center p-3">© 2023 Copyright: Hella Co.</div>
        <!-- links -->
        <div class="links">
            <a href="/"> CONTACT US </a>
            <a href="/">STORE LOCATOR</a>
            <a href="/">TRACK ORDER</a>
            <a href="/">SIGN IN</a>
        </div>
    </footer>
</template>

<style>
    footer {
        background-color: black;
        color: white;
        position: fixed;
        bottom: 0;
        left: 0;
        width: 100%;

        text-align: center;
        background-color: rgb(21, 19, 19);
    }

    a {
        color: white;
    }
    .links {
        display: flex;
        justify-content: space-evenly;
        direction: rtl;
    }
</style>
