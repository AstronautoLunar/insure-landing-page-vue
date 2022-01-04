<template>
  <div id="render">
    <Header
      :showMenuMobile="showMenuMobile"
      :showNavigation="toggleNavigation"
      :modeOn="navigation"
    />
    <NavBarMobile
      :show="navigation"
    />
    <Main/>
    <Footer/>
  </div>
</template>

<script>
  import Header from "./components/Header/Header.vue";
  import Main from "./components/Main/Main.vue";
  import Footer from "./components/Footer/Footer.vue";
  import NavBarMobile from "./components/NavBarMobile/NavBarMobile.vue";

  export default {
    name: 'App',
    components: {
      Header,
      Main,
      Footer,
      NavBarMobile
    },
    data() {
      return {
        mediaQuerieList: matchMedia("(max-width: 842px)"),
        showMenuMobile: false,
        navigation: false
      }
    },
    methods: {
      toggleModeMobile(mediaQuerieList) {
        if(mediaQuerieList.matches) {
            this.showMenuMobile = true;
        } else {
            this.showMenuMobile = false
        }
      },
      toggleNavigation() {
        this.navigation = !this.navigation;
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

<style>
  * {
    margin: 0;
    padding: 0;

    box-sizing: border-box;

    font-family: Arial, Helvetica, sans-serif;
  }

  :root {
    /* Primary */
    --dark-violet: hsl(256, 26%, 20%);
    --grayish-blue: hsl(216, 30%, 68%);

    /* Neutral */
    --very-dark-violet: hsl(270, 9%, 17%);
    --dark-grayish-violet: hsl(273, 4%, 51%);
    --very-light-gray: hsl(0, 0%, 98%);
  }

</style>
