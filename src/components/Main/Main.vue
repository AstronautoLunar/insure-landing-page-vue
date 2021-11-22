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

        <Container>
            <div id="main-secure-content">
                <section 
                    id="" 
                    class="section"
                >
                    <Line
                        color="var(--very-dark-violet)"
                    />

                </section>
            </div>
        </Container>
    </main>
</template>

<script>
    import Container from "../Container/Container.vue";
    import Button from "../Button/Button.vue";
    import Line from "../Line/Line.vue";

    export default {
        name: "Main",
        components: {
            Container,
            Button,
            Line
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
    #presentation-content-secure
    {
        width: 100%;
    }

    #presentation {
        padding: 100px 0;
        margin-bottom: 100px;

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
    }
</style>