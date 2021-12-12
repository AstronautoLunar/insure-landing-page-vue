<template>
    <button 
        class="custom-button"
        :style="{
            borderColor: color
        }"
    >
        <span
            class="text"
            :style="{
                color,
            }"
        >
            <slot>

            </slot>
        </span>
    </button>
</template>

<script>

    export default {
        name: "Button",
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

    .custom-button {
        background-color: transparent;
        outline: none;
        box-shadow: none;

        padding: 10px 30px;

        border-width: 2px;
        border-style: solid;
        border-color: var(--very-dark-violet);
    }

    .text {
        font-weight: 700;
        font-family: Karla, Helvetica, sans-serif;
        font-size: 1rem;
    }

</style>
