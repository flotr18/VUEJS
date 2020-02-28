<template>
    <div>
        <v-container fluid grid-list-md>


        <v-flex d-flex>

        <v-layout row jusitfy-center>


        <v-flex 2 id="hello" v-for="team in teams" v-bind:key="team">
            <div id="card">
                <img v-bind:src="team.img" v-bind:alt="team.name" id="team">
                <p id="name"> {{ team.name }} </p>
                <p id="engine"> {{ team.engine }} </p>
            </div>

        </v-flex>
        </v-layout>
        </v-flex>
        </v-container>
    </div>

</template>

<script>
    export default {
        name: "test",
        data : function () {
            return {
                teams : [

                    { name : "Mercedes AMG Petronas Formula One Team", car : "W11", engine : "Mercedes" , img : "https://d3qmgl49lqmtd9.cloudfront.net/live/tst18d2/mercedes.png"},
                    { name : "Scuderia Ferrari Mission Winnow", car : "SF1000", engine : "Ferrari", img : "https://d3qmgl49lqmtd9.cloudfront.net/live/tst18d2/ferrari.png"},
                    { name : "Aston Martin Red Bull Racing", car : "RB16",  engine : "Honda", img : "https://d3qmgl49lqmtd9.cloudfront.net/live/tst18d2/redbull.png"},

                    { name : "McLaren F1 Team", car : "MCL35", engine : "Renault", img : "https://d3qmgl49lqmtd9.cloudfront.net/live/tst18d2/mclaren.png"},
                    { name : "Renault F1 Team", car : "RS20", engine : "Renault", img : "https://d3qmgl49lqmtd9.cloudfront.net/live/tst18d2/renault.png"},

                    { name : "Scuderia AlphaTauri Honda", car : "AT01", engine : "Honda", img : "https://d3qmgl49lqmtd9.cloudfront.net/live/tst18d2/alphatauri.png"},
                    { name : "BWT Racing Point F1 Team", car : "RP20", engine : "Mercedes", img : "https://d3qmgl49lqmtd9.cloudfront.net/live/tst18d2/racingpoint.png"},
                    { name : "Alfa Romeo Racing Orlen", car : "C39", engine : "Ferrari", img : "https://d3qmgl49lqmtd9.cloudfront.net/live/tst18d2/alfaromeo.png"},
                    { name : "Haas F1 Team", car : "VF-20", engine : "Ferrari", img : "https://d3qmgl49lqmtd9.cloudfront.net/live/tst18d2/haas.png"},

                    { name : "ROKiT Williams Racing", car : "FW43", engine : "Mercedes", img : "https://d3qmgl49lqmtd9.cloudfront.net/live/tst18d2/williams.png"},


                ]
            }

        }


    }


</script>

<style scoped>

    #card {
        height: 150px;
        width: 300px;
        background-color: #555;
        border-radius: 10px;
        text-align: center;




    }

    #card:hover {
        background-color: red;
        transition: 0.5s ease;
        cursor: pointer;
    }

    #name {
        font-weight: bold;
        margin-top: 5px;
        font-family: F1Font, sans-serif;
        font-size: 20px;

    }

    #engine {
        font-family: F1Font, sans-serif;
        margin-top: 5px;
        font-weight: bold;
    }

    #team {
        margin-top: 10px;
    }

    #hello {
        margin-top: 10px;
        display: block;
    }



</style>