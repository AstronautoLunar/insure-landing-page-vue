<template>
    <div 
        class="line"
        :style="{
            backgroundColor: color
        }"
    >
    </div>
</template>

<script>

    export default {
        name: "Line",
        components: {

        },
        props: {
            color: {
                type: String,
                required: false
            }
        }
    }

</script>

<style scoped>

    .line {
        width: 125px;
        height: 2px;

        background-color: var(--very-light-gray);

        opacity: 0.2;
    }

</style>
