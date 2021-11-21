<template>
    <header id="header">
        <Container>
            <div id="content">
                <img
                    :src="require('../../assets/logo.svg')"
                    alt="Logo"
                />

                <nav id="navBar">
                    <ul id="list">
                        <li 
                            class="item"
                            v-for="item in itemsListNavBar"
                            :key="item.id"
                        >
                            <a>
                                {{ item.name }}
                            </a>
                        </li>
                    </ul>
                </nav>
            </div>
        </Container>
    </header>
</template>

<script>
    import Container from '../Container/Container.vue';

    export default {
        name: "Header",
        components: {
            Container
        },
        data() {
            return {
                itemsListNavBar: [
                    {
                        id: 1,
                        name: "HOW WE WORK",
                    },
                    {
                        id: 2,
                        name: "BLOG",
                    },
                    {
                        id: 3,
                        name: "ACCOUNT",
                    },
                    {
                        id: 4,
                        name: "VIEW PLANS",
                    }
                ]
            }
        }
    }

</script>

<style scoped>

    #header {
        justify-content: center;

        height: 80px;
    }

    #header,
    #content,
    #list
    {
        display: flex;
        align-items: center;
    }

    #header,
    #content
    {
        
        width: 100%;
    }

    #content {
        height: 100%;

        justify-content: space-between;
    }

    #list {
        justify-content: center;
    }

    .item {
        list-style-type: none;
    }

    .item > a {
        text-decoration: none;

        padding: 10px 30px;
        
        font-size: 15px;
    }

    .item:last-of-type > a {
        border: 2px solid var(--very-dark-violet);

        font-weight: bold;
    }

</style>