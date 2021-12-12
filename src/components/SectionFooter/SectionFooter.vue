<template>
    <div class="SectionFooter">
        <span class="title">
            {{ title }}
        </span>
        <a 
            class="link"
            v-for="item in data"
            :key="item.id"
            href="#"
        >
            {{ item.text }}
        </a>
    </div>
</template>

<script>

    export default {
        name: "SectionFooter",
        components: {

        },
        props: {
            data: {
                type: Array,
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
    
    .SectionFooter {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: flex-start;
    }

    .title {
        color: var(--dark-grayish-violet);

        margin-bottom: 24px;
    }

    .title,
    .link
    {
        font-family: Karla, Helvetica, sans-serif;
        font-weight: 700;
        font-size: 1rem;
    }

    .link {
        margin-bottom: 16px;

        text-decoration: none;
        color: var(--very-dark-violet);
    }

    .link:last-of-type {
        margin-bottom: 0;
    }

</style>