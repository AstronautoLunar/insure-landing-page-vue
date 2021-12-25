<template>
    <main id="main">
        <section 
            id="presentation" 
            class="section"
        >
            <Container>
                <div id="presentation-content-secure">
                    <Line/>
                    <h1 id="title">
                        Humanizing your insurance
                    </h1>
                    <p id="description">
                        Get your life insurance coverage easier and faster. We blend our expertise and technology to help you find the plan that's right for you. Ensure you and your loved ones are protected.
                    </p>
                    <Button
                        color="var(--very-light-gray)"
                        colorTextBackgroundOn="var(--very-dark-violet)"
                    >
                        VIEW PLANS
                    </Button>
                    <img
                        id="image-presentation-desktop"
                        :src="require('../../assets/image-intro-desktop.jpg')"
                        alt="Image family walking together"
                    />
                </div>
            </Container>

            <img
                v-for="item in imagesSectionPresentation"
                :key="item.id"
                :src="item.source"
                :id="item.position"
                :alt="item.alt"
            />
        </section>

        <Container identifier="body-container">
            <div id="main-secure-content">
                <section 
                    id="section-benefits" 
                    class="section"
                >
                    <Line
                        color="var(--very-dark-violet)"
                    />

                    <h1 id="title-section-benefits">
                        We're different
                    </h1>

                    <div id="area-benefits-cards">
                        <CardBenefits
                            v-for="item in benefitsCards"
                            :key="item.id"
                            :icon="item.icon"
                            :title="item.title"
                        >
                            {{ item.description }}
                        </CardBenefits>
                    </div>
                </section>
            </div>

            <AreaInvitation>
                Find out more about how we work
            </Areainvitation>
        </Container>
    </main>
</template>

<script>
    import Container from "../Container/Container.vue";
    import Button from "../Button/Button.vue";
    import Line from "../Line/Line.vue";
    import CardBenefits from "../CardBenefits/CardBenefits.vue";
    import AreaInvitation from "../AreaInvitation/AreaInvitation.vue";

    export default {
        name: "Main",
        components: {
            Container,
            Button,
            Line,
            CardBenefits,
            AreaInvitation
        },
        data() {
            return {
                imagesSectionPresentation: [
                    {
                        id: 1,
                        position: "right",
                        source: require('../../assets/bg-pattern-intro-right-desktop.svg'),
                        alt: "line circle"
                    },
                    {
                        id: 2,
                        position: "left",
                        source: require('../../assets/bg-pattern-intro-left-desktop.svg'),
                        alt: "line circle"
                    },
                ],
                benefitsCards: [
                    {
                        id: 1,
                        icon: require('../../assets/icon-snappy-process.svg'),
                        title: "Snappy Process",
                        description: "Our application process can be completed in minutes, not hours. Don't get stuck filling in tedios forms"
                    },
                    {
                        id: 2,
                        icon: require('../../assets/icon-affordable-prices.svg'),
                        title: "Affordable Prices",
                        description: "We don't want you worrying about high monthly costs. Our prices may be low, but we still offer the best coverage possible."
                    },
                    {
                        id: 3,
                        icon: require('../../assets/icon-people-first.svg'),
                        title: "People First",
                        description: "Our plans aren't full of confitions and clauses to prevent payouts. We make sure you're covered when you need it."
                    }
                ]
            }
        }
    }

</script>

<style scoped>

    #main,
    #presentation
    {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
    }

    .section,
    #presentation,
    #main,
    #presentation-content-secure,
    #main-secure-content,
    .area-benefits-cards
    {
        width: 100%;
    }

    #presentation {
        padding: 100px 0;
        margin-bottom: 200px;

        background-color: var(--dark-violet);

        z-index: -2;

        position: relative;
    }

    #presentation h1,
    #presentation p
    {
        color: var(--very-light-gray);
    }

    #presentation-content-secure {
        position: relative;
    }

    #title {
        width: 350px;
    
        font-size: 3rem;
        font-family: "DM Serif Display";

        margin-top: 50px;

    }

    #description {
        margin: 30px 0;

        line-height: 25px;

        font-family: Karla;

        width: 510px;
    }

    #image-presentation-desktop {
        position: absolute;
        right: 0;
        top: 0;

        width: 450px;
    }

    #right {
        right: 0;
        top: 0;
        
        z-index: 0;

        width: 330px;
    }

    #right,
    #left
    {
        position: absolute;
    }

    #left {
        left: 0;
        bottom: -300px;

        z-index: -1;
    }

    #title-section-benefits {
        font-size: 3rem;
        font-family: "DM Serif Display", Helvetica, sans-serif;
        
        margin-top: 24px;
        margin-bottom: 40px;
    }

    #section-benefits
    {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: flex-start;
    }

    #area-benefits-cards {
        display: flex;
        justify-content: space-between;
        align-items: center;
    }

    #body-container {
        flex-direction: column;
    }

</style>