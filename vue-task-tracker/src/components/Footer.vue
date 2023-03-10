<template>
    <footer>
        <p1 class="text">Copyright &copy; 2023</p1>
        <router-link class="link" to="/about">About</router-link>
    </footer>
</template>

<style scoped>
    a {
        color: #333;

    }
    footer {
        margin-top: 30px;
        text-align: center;
    }
    .text::after {
        content: "\a";
        white-space: pre;
    }
</style>