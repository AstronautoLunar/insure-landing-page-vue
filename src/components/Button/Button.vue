<template>
    <button 
        :class="`custom-button ${isTransition ? 'transition' : ''}`"
        :style="{
            borderColor: color,
            backgroundColor: isBackground ? color : 'transparent'
        }"
        @mouseenter="changeBackground(true)"
        @mouseleave="changeBackground(false)"
    >
        <span
            class="text"
            :style="{
                color: isBackground ? colorTextBackgroundOn : color
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
            },
            isTransition: {
                type: Boolean,
                required: false,
                default: true
            },
            colorTextBackgroundOn: {
                type: String,
                required: true,
            }
        },
        data() {
            return {
                isBackground: false
            }
        },
        methods: {
            changeBackground(value) {
                this.isBackground = value;
            }
        }
    }

</script>

<style scoped>

    .custom-button {
        background-color: transparent;
        outline: none;
        box-shadow: none;

        z-index: 1000;

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

    .transition {
        transition: background-color 500ms;
    }

</style>
