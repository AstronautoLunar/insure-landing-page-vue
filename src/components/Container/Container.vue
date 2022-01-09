<template>
    <div
        :id="identifier"
        class="container"
        :style="{
            width: modeMobile ? '100%' : '80%'
        }"
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
        },
        data() {
            return {
                mediaQuerieList: matchMedia("(max-width: 562px)"),
                modeMobile: false
            }
        },
        methods: {
            toggleModeMobile(mediaQuerieList) {
                if(mediaQuerieList.matches) {
                    this.modeMobile = true;
                } else {
                    this.modeMobile = false;
                }
            }
        },
        mounted() {
            this.toggleModeMobile(this.mediaQuerieList);

            this.mediaQuerieList.addEventListener("change", this.toggleModeMobile);
        },
        updated() {
            this.mediaQuerieList.addEventListener("change", this.toggleModeMobile);
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

        transition: width 500ms;
    }
    
</style>