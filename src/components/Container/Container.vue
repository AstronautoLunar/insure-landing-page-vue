<template>
    <div id="container">
        <slot>

        </slot>
    </div>
</template>

<script>

    export default {
        name: "Container",
        components: {

        }
    }

</script>

<style scoped>

    #container {
        width: 80%;
        height: 100%;

        display: flex;
        justify-content: center;
        align-items: center;
    }

</style>