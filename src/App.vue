<template>


        <div id="app">
    <h1 id="title">F1 2020 GRID </h1>

    <test></test>

  </div>


</template>

<script>

  import  test from './components/test.vue'


  export default {
    name: 'App',
    components: {
      test



    }
  }
</script>

<style>

  body {
    background-color: #19161F;
  }

  @font-face {
    font-family: F1Font;
    src: url("assets/Formula1-Regular_web_0.ttf");
  }

  #title {
    font-family: F1Font,sans-serif;
    color: red;
    text-align: center;
  }




</style>