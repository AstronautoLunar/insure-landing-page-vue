<template>
    <div class="CardBenefits">
        <div 
            class="benefit-card"
        >
            <div class="circle-icon">
                <img
                    :src="icon"
                    :alt="`Image ${ title }`"
                />
            </div>
            <h1>
                {{ title }}
            </h1>
            <span>
                <slot>

                </slot>
            </span>
        </div>
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
    .benefit-card
    {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: flex-start;
    }

    /* .benefit-card {
        flex: 1;
        
        margin-right: 20px;
    }

    .benefit-card:last-of-type {
        margin-right: 0;
    } */

</style>