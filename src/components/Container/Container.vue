<template>
    <div
        :id="identifier"
        class="container"
    >
        <slot>

        </slot>
    </div>
</template>

<script>

    export default {
        name: "Container",
        components: {

        },
        props: {
            identifier: {
                type: String,
                require: false
            }
        }
    }

</script>

<style scoped>

    .container {
        width: 80%;
        height: 100%;

        display: flex;
        justify-content: center;
        align-items: center;
    }

</style>