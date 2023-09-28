<template>
    <FrontPage />
</template>

<script>
import FrontPage from "@/features/FrontPage";

export default {
    name: 'App',
    components: {
        FrontPage,
    }
}
</script>

<style>
html, body {
    height: 100%;
}
body{
    margin: 0;
    overflow: auto;
}
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    height: 100%;
}
</style>
