<template>
    <header id="header">
        <Container>
            <div id="header-content">
                <img
                    id="logo"
                    :src="require('../../assets/logo.svg')"
                    alt="Logo"
                />

                <MenuMobile
                    :isVisible="showMenuMobile"
                    id="menuMobile"
                />

                <nav 
                    id="navBar"
                    v-show="!showMenuMobile"
                >
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
                        <li class="item">
                            <Button
                                color="var(--very-dark-violet)"
                                colorTextBackgroundOn="var(--very-light-gray)"
                            >
                                VIEW PLANS
                            </Button>
                        </li>
                    </ul>
                </nav>
            </div>
        </Container>
    </header>
</template>

<script>
    import Container from '../Container/Container.vue';
    import Button from '../Button/Button.vue';
    import MenuMobile from '../MenuMobile/MenuMobile.vue';

    export default {
        name: "Header",
        components: {
            Container,
            Button,
            MenuMobile
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
                    }
                ],
                mediaQuerieList: matchMedia("(max-width: 842px)"),
                showMenuMobile: false
            }
        },
        methods: {
            toggleModeMobile(mediaQuerieList) {
                if(mediaQuerieList.matches) {
                    this.showMenuMobile = true;
                } else {
                    this.showMenuMobile = false
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

    #header {
        justify-content: center;

        height: 80px;

        z-index: 1;

        background-color: white;
    }

    #header,
    #header-content,
    #list
    {
        display: flex;
        align-items: center;
    }

    #header,
    #header-content
    {
        
        width: 100%;
    }

    #header-content {
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

        color: var(--dark-grayish-violet);

        padding: 10px 30px;
        
        font-size: 15px;
        font-family: Karla, Helvetica, sans-serif;
        font-weight: 700;
    }

    .item:last-of-type > a {
        border: 2px solid var(--very-dark-violet);

        font-weight: bold;
    }

    @media screen and (max-width: 562px) {
        #logo {
            margin-left: 25px;
        }
        
        #menuMobile {
            margin-right: 25px;
        }
    }

</style>