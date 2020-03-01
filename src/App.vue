<template>


        <div id="app" v-bind:style="{ backgroundColor: activeColor}">
    <h1 id="title">F1 2020 GRID </h1>
            <button @click="darktheme">Black theme</button>

    <test></test>
    <chart></chart>

  </div>


</template>

<script>

  import  test from './components/test.vue'



  export default {
    name: 'App',
    components: {
      test,

    },
      data() {
        return {
            activeColor : 'white'
        }
      },

      methods : {

        darktheme : function () {

            if (this.activeColor === 'white'){

                this.activeColor = '#252525'
            }
            else {
                this.activeColor = 'white'
            }

        }
      }

  }




</script>

<style>



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