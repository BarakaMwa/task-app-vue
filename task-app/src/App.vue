<template>
    <div class="align-content-center">
        Hello {{firstName}}
    </div>
</template>

<script>

    export default {
        data() {
            return {
                firstName: "Baraka",
                lastName: "Mwangamba",
                gender: "male",
            }
        },
        name: 'App',
        components: {}
    }
</script>

<style>
    /*#app {
        font-family: Avenir, Helvetica, Arial, sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        text-align: center;
        color: #2c3e50;
        margin-top: 60px;
    }*/
</style>
