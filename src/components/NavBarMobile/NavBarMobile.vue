<template>
    <div 
        class="NavBarMobile"
        :style="{
            height: show ? '500px' : '0px'
        }"
    >
        <ul class="list">
            <li
                class="item"
                v-for="item in items"
                :key="item.id"
            >
                <a 
                    class="link"
                    
                >
                    {{ item.text }}
                </a>
            </li>
            <li class="item">
                <Button
                    identifier="button"
                    color="var(--very-light-gray)"
                    colorTextBackgroundOn="var(--very-dark-violet)"
                >
                    VIEW PLANS
                </Button>
            </li>
        </ul>
        
    </div>
</template>

<script>
    import Button from "../Button/Button.vue";

    export default {
        name: "NavBarMobile",
        components: {
            Button
        },
        data() {
            return {
                items: [
                    {
                        id: "01",
                        text: "HOW WE WORK"
                    },
                    {
                        id: "02",
                        text: "BLOG"
                    },
                    {
                        id: "03",
                        text: "ACCOUNT"
                    },
                ]
            }
        },
        props: {
            show: {
                type: Boolean,
                required: true
            }
        }
    }

</script>

<style scoped>

    .NavBarMobile {
        width: 100%;
        height: 0px;

        background-color: var(--dark-violet);

        overflow: hidden;

        transition: height 500ms;
    }

    .list {
        width: 100%;
        height: 100%;

        display: flex;
        flex-direction: column;
        justify-content: flex-start;
        align-items: center;

        list-style-type: none;
    }

    .item {
        margin-top: 20px;
        padding: 10px 20px;

        width: 100%;

        text-align: center;
    }

    .item,
    #button
    {
        width: 100%;
    }

    .link {
        color: var(--very-light-gray);

        font-weight: bold;
    }

    #button {
        max-width: 100%;
        padding: 20px;
    }

</style>