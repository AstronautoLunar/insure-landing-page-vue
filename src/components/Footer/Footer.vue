<template>
    <footer id="footer">
        <Container identifier="container-footer">
            <div id="area-social-media">
                <img
                    :src="require('../../assets/logo.svg')"
                    alt="logo"
                />

                <div id="social-networks">
                    <img
                        class="icon-social-media"
                        v-for="item in imagesSocialMedia"
                        :key="item.id"
                        :src="item.src"
                        :alt="item.alt"
                    />
                </div>
            </div>
            <Line
                :isFullWidth="true"
                color="var(--dark-grayish-violet)"
            />
            <div id="sections-of-footer">
                <SectionFooter
                    v-for="item in sectionsOfFooter"
                    :key="item.id"
                    :title="item.title"
                    :data="item.sections"
                />
            </div>
        </Container>
    </footer>
</template>

<script>
    import Container from "../Container/Container.vue";
    import Line from "../Line/Line.vue";
    import SectionFooter from "../SectionFooter/SectionFooter.vue";

    export default {
        name: "Footer",
        components: {
            Container,
            Line,
            SectionFooter
        },
        data() {
            return {
                imagesSocialMedia: [
                    {
                        id: 1,
                        src: require("../../assets/icon-facebook.svg"),
                        alt: "icon facebook"
                    },
                    {
                        id: 2,
                        src: require("../../assets/icon-twitter.svg"),
                        alt: "icon twitter"
                    },
                    {
                        id: 3,
                        src: require("../../assets/icon-pinterest.svg"),
                        alt: "icon pinterest"
                    },
                    {
                        id: 4,
                        src: require("../../assets/icon-instagram.svg"),
                        alt: "icon instagram"
                    },
                ],
                sectionsOfFooter: [
                    {
                        id: 1,
                        title: "OUR COMPANY",
                        sections: [
                            {
                                id: 1,
                                text: "HOW WE WORK"
                            },
                            {
                                id: 2,
                                text: "WHY INSURE?"
                            },
                            {
                                id: 3,
                                text: "VIEW PLANS"
                            },
                            {
                                id: 4,
                                text: "REVIEWS"
                            },
                        ]
                    },
                    {
                        id: 2,
                        title: "HELP ME",
                        sections: [
                            {
                                id: 1,
                                text: "FAQ"
                            },
                            {
                                id: 2,
                                text: "TERMS OF USE"
                            },
                            {
                                id: 3,
                                text: "PRIVACY POLICY"
                            },
                            {
                                id: 4,
                                text: "COOKIES"
                            },
                        ],
                    },
                    {
                        id: 3,
                        title: "CONTACT",
                        sections: [
                            {
                                id: 1,
                                text: "SALES"
                            },
                            {
                                id: 2,
                                text: "SUPPORT"
                            },
                            {
                                id: 3,
                                text: "LIVE CHAT"
                            }
                        ],
                    },
                    {
                        id: 4,
                        title: "OTHERS",
                        sections: [
                            {
                                id: 1,
                                text: "CAREERS"
                            },
                            {
                                id: 2,
                                text: "PRESS"
                            },
                            {
                                id: 3,
                                text: "LICENSES"
                            }
                        ],
                    }
                ]
            }
        }
    }

</script>

<style scoped>

    #footer {
        width: 100%;
        height: 400px;

        background-color: var(--very-light-gray);

        flex-direction: column;
        justify-content: center;
    }

    #footer,
    #area-social-media,
    #sections-of-footer
    {
        display: flex;
        align-items: center;
    }
    

    #container-footer {
        flex-direction: column;
    }

    #area-social-media {
        justify-content: space-between;

        margin-bottom: 24px;
    }

    .icon-social-media {
        width: 25px;
        
        margin: 0 10px;
    }

    #area-social-media,
    #sections-of-footer
    {
        width: 100%;
    }

    #sections-of-footer {
        margin-top: 40px;

        justify-content: space-between;
    }
</style>