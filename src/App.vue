<template>
  <div id="render">
    <Header/>
    <Main/>
  </div>
</template>

<script>
  import Header from "./components/Header/Header.vue";
  import Main from "./components/Main/Main.vue";

  export default {
    name: 'App',
    components: {
      Header,
      Main
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
