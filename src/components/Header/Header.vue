<template>
    <header id="header">
        <Container>
            <div id="header-content">
                <img
                    id="logo"
                    :src="require('../../assets/logo.svg')"
                    alt="Logo"
                />

                <ButtonMenuMobile
                    @showNavigation="showNavigation"
                    :isVisible="showMenuMobile"
                    id="ButtonMenuMobile"
                    :modeOn="modeOn"
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
    import ButtonMenuMobile from '../ButtonMenuMobile/ButtonMenuMobile.vue';

    export default {
        name: "Header",
        components: {
            Container,
            Button,
            ButtonMenuMobile
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
                
            }
        },
        props: {
            showMenuMobile: {
                type: Boolean,
                required: true
            },
            showNavigation: {
                type: Function,
                required: false
            },
            modeOn: {
                type: Boolean,
                required: false
            }
        },
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
        
        #ButtonMenuMobile {
            margin-right: 25px;
        }
    }

</style>