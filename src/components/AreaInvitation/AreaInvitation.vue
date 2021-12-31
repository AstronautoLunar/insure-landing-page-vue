<template>
    <div class="AreaInvitation">
        <h1 class="title">
            <slot>

            </slot>
        </h1>

        <Button
            color="var(--very-light-gray)"
            colorTextBackgroundOn="var(--very-dark-violet)"
        >
            HOW WE WORK
        </Button>

        <img
            class="illustration-lines"
            :src="require('../../assets/bg-pattern-how-we-work-desktop.svg')"
            alt="lines illustration"
        />
    </div>
</template>

<script>
    import Button from "../Button/Button.vue";

    export default {
        name: "AreaInvitation",
        components: {
            Button
        }
    }

</script>

<style scoped>

    .AreaInvitation {
        width: 100%;
        height: 150px;

        display: flex;
        justify-content: space-between;
        align-items: center;
    
        background-color: var(--dark-violet);

        padding: 115px 85px;

        margin: 150px 0;

        position: relative;

        overflow: hidden;
    }

    .title {
        color: var(--very-light-gray);

        max-width: 300px;
    }

    .illustration-lines {
        position: absolute;
        top: 50%;
        right: 0;
        transform: translateY(-50%);
    }

    @media screen and (max-width: 562px) {
        .AreaInvitation {
            margin: 150px 20px;
        }
    }

</style>