<template>
    <div 
        class="line"
        :style="{
            backgroundColor: color,
            width: isFullWidth ? '100%' : '125px'
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
            },
            isFullWidth: {
                type: Boolean,
                required: false,
                default: false
            }
        }
    }

</script>

<style scoped>

    .line {
        height: 2px;

        background-color: var(--very-light-gray);

        opacity: 0.2;
    }

</style>
