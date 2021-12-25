<template>
    <div 
        class="MenuMobile"
        v-show="isVisible"
    >
        <div class="line"></div>
        <div class="line"></div>
        <div class="line"></div>
    </div>
</template>

<script>

    export default {
        name: "MenuMobile",
        components: {

        },
        props: {
            isVisible: {
                type: Boolean,
                required: false,
                default: true
            }
        }
    }

</script>

<style scoped>

    .MenuMobile {
        width: 50px;

        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;

        padding: 10px;

        border: 3px solid var(--very-dark-violet);
    }

    .line {
        width: 90%;
        height: 3px;

        margin-top: 5spx;
        margin-bottom: 5px;

        background-color: var(--very-dark-violet);
    }

    .line:first-of-type {
        margin-top: 0;
    }

    .line:last-of-type {
        margin-bottom: 0;
    }

</style>