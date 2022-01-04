<template>
    <div class="AreaInvitation">
        <h1 class="title">
            <slot>

            </slot>
        </h1>

        <Button
            identifier="button-section-invite"
            color="var(--very-light-gray)"
            colorTextBackgroundOn="var(--very-dark-violet)"
        >
            HOW WE WORK
        </Button>

        <img
            class="illustration-lines"
            :src="require(`../../assets/bg-pattern-how-we-work-${isChangeBackgroundImage ? 'mobile' :  'desktop'}.svg`)"
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
        },
        data() {
            return {
                mediaQuerieList: matchMedia("(max-width: 562px)"),
                isChangeBackgroundImage: false
            }
        },
        methods: {
            toggleBackgroundImage(mediaQuerieList) {
                if(mediaQuerieList.matches) {
                    this.isChangeBackgroundImage = true;
                } else {
                    this.isChangeBackgroundImage = false;
                }
            }
        },
        mounted() {
            this.toggleBackgroundImage(this.mediaQuerieList);

            this.mediaQuerieList.addEventListener("change", this.toggleBackgroundImage);
        },
        updated() {
            this.mediaQuerieList.addEventListener("change", this.toggleBackgroundImage);
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

    @media screen and (max-width: 914px) {
        #button-section-invite {
            margin-left: 85px;
        }
    }

    @media screen and (max-width: 786px) {
        .AreaInvitation {
            margin: 150px 20px;
            padding: 64px 32px;

            flex-direction: column;

            height: auto;
        }
        
        .title {
            text-align: center;

            margin-right: 0;

            margin-bottom: 32px;
        }

        #button-section-invite {
            margin-left: 0;
        }

        .illustration-lines {
            height: 275px;

            top: 0;
            right: 0;

            transform: none;
        }

    }

    /* @media screen and (max-width: 562px) {
    } */

</style>