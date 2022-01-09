<template>
    <div class="CardBenefits">
        <img
            :src="icon"
            :alt="`Image ${ title }`"
        />
        <h1 class="title">
            {{ title }}
        </h1>
        <span class="description">
            <slot>

            </slot>
        </span>
    </div>
</template>

<script>

    export default {
        name: "CardBenefits",
        components: {

        },
        props: {
            icon: {
                type: String,
                required: true
            },
            title: {
                type: String,
                required: true
            }
        }
    }

</script>

<style scoped>

    .CardBenefits {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: flex-start;

        max-width: 31%;
    }

    .title {
        margin-top: 24px;
        margin-bottoM: 16px;
        
        font-family: "DM Serif Display", Helvetica, sans-serif;
    }

    .description {
        font-family: Karla, Helvetica, sans-serif;
        font-weight: bold;

        color: var(--dark-grayish-violet);
    }

    @media screen and (max-width: 562px) {
        .CardBenefits {
            max-width: 100%;

            margin-bottom: 48px;

            align-items: center;
        }

        .CardBenefits:last-of-type {
            margin-bottom: 0;
        }

        .title,
        .description
        {
            text-align: center;
        }
    }

</style>