<template>


    <div id="app" v-bind:style="{ backgroundColor: activeColor}">
        <h1 id="title">F1 2020 GRID </h1>
        <div id="test">

        </div>
        <v-btn v-bind:style="{color : textColor}" v-bind:dark="true" color="rgb(37,37,37)" right="true" @click="darktheme">{{ theme }}</v-btn>

        <test></test>

        <div id="blank">

        </div>


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
                activeColor : 'white',
                textColor :  'white',
                theme : 'Dark theme'
            }
        },
        methods : {
            darktheme : function () {
                if (this.activeColor === 'white'){

                    this.activeColor = '#252525';
                    this.textColor = 'white';
                    this.theme = 'Light Theme';
                }
                else {
                    this.activeColor = 'white';
                    this.textColor = 'white';
                    this.theme = 'Dark Theme'
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

    #blank {
        height: 100px;
    }

</style>