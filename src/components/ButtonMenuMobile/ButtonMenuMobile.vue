<template>
    <div 
        class="ButtonMenuMobile"
        v-show="isVisible"
        @click="$emit('showNavigation')"
        :style="{
            height: modeOn && '50px'

        }"
    >
        <div 
            class="line"
            :style="modeOn && rotateLine('left')"
        ></div>
        <div 
            class="line"
            :style="modeOn && rotateLine('left')"
        ></div>
        <div 
            class="line"
            :style="modeOn && rotateLine('right')"
        ></div>
    </div>
</template>

<script>

    export default {
        name: "ButtonMenuMobile",
        components: {

        },
        props: {
            isVisible: {
                type: Boolean,
                required: false,
                default: false
            },
            modeOn: {
                type: Boolean,
                required: false,
                default: false
            }
        },
        methods: {
            rotateLine(directionRotate) {
                switch(directionRotate) {
                    default:
                    case "right":
                        return {
                            transform: "rotate(45deg)",
                            left: "0px",
                            right: "0px",
                            top: "0px",
                            bottom: "0px",
                            margin: "auto"
                        };
                    case "left":
                        return {
                            transform: "rotate(-45deg)",
                            left: "0px",
                            right: "0px",
                            top: "0px",
                            bottom: "0px",
                            margin: "auto"
                        };
                }
            }
        }
    }

</script>

<style scoped>

    .ButtonMenuMobile {
        width: 50px;
        height: 50px;

        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;

        padding: 10px;

        border: 3px solid var(--very-dark-violet);
        
        position: relative;
    }

    .line {
        width: 60%;
        height: 3px;

        margin-bottom: 5px;

        background-color: var(--very-dark-violet);
        
        position: absolute;

        transition: all 500ms;
    }

    .line:nth-of-type(1) {
        top: 25%;
        bottom: 75%;
    }

    .line:nth-of-type(2) {
        top: 50%;
        bottom: 50%;
    }

    .line:nth-of-type(3) {
        top: 75%;
        bottom: 25%;
    }

    .line:last-of-type {
        margin-bottom: 0;
    }

</style>