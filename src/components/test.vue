<template>
    <div>

        <v-carousel class="diapo"
                    :show-arrows="false">
            <v-carousel-item
                    v-for="(diapo,i) in diapos "
                    :key="i"
                    :src="diapo.picture"
            >


            </v-carousel-item>

        </v-carousel>


        <h3 class="subtitle">TEAMS </h3>

        <v-container fluid grid-list-md>

            <v-flex d-flex>

                <v-layout row jusitfy-center>


                    <v-flex 4 id="hello" v-for="team in teams" v-bind:key="team">
                        <div class="card">
                            <img v-bind:src="team.img" v-bind:alt="team.name" class="team">
                            <p class="name"> {{ team.name }} </p>
                            <p class="engine"> {{ team.car }} - {{ team.engine }}</p>
                        </div>



                    </v-flex>
                </v-layout>
            </v-flex>
        </v-container>

        <div class="buttons-main">
            <v-btn @click="ShowMain" class="buttons-component">Show</v-btn>
            <v-btn @click="DeleteMain" class="buttons-component">Delete</v-btn>
            <v-btn @click="showOthers" v-bind:style="{ visibility : showButtons}" class="buttons-component">TOP TEAMS</v-btn>
            <v-btn @click="showBests" v-bind:style="{ visibility : showButtons}" class="buttons-component">Others</v-btn>


        </div>







        <h3 class="subtitle">{{ first }}</h3>




        <v-container fluid grid-list-md v-if="read">

            <v-flex d-flex>

                <v-layout row jusitfy-center>


                    <v-flex 4 id="hello" v-for="team in topTeams" v-bind:key="team">
                        <div class="card">
                            <img v-bind:src="team.img" v-bind:alt="team.name" class="team">
                            <p class="name"> {{ team.name }} </p>
                            <p class="engine"> {{ team.car }} - {{ team.engine }}</p>
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
                    { name : "Mercedes AMG Petronas Formula One Team", car : "W11", engine : "Mercedes" , img : "https://d3qmgl49lqmtd9.cloudfront.net/live/tst18d2/mercedes.png" , top : true},
                    { name : "Scuderia Ferrari Mission Winnow", car : "SF1000", engine : "Ferrari", img : "https://d3qmgl49lqmtd9.cloudfront.net/live/tst18d2/ferrari.png", top : true},
                    { name : "Aston Martin Red Bull Racing", car : "RB16",  engine : "Honda", img : "https://d3qmgl49lqmtd9.cloudfront.net/live/tst18d2/redbull.png", top : true},
                    { name : "McLaren F1 Team", car : "MCL35", engine : "Renault", img : "https://d3qmgl49lqmtd9.cloudfront.net/live/tst18d2/mclaren.png", top : false},
                    { name : "Renault F1 Team", car : "RS20", engine : "Renault", img : "https://d3qmgl49lqmtd9.cloudfront.net/live/tst18d2/renault.png",top : false},
                    { name : "Scuderia AlphaTauri Honda", car : "AT01", engine : "Honda", img : "https://d3qmgl49lqmtd9.cloudfront.net/live/tst18d2/alphatauri.png",top : false},
                    { name : "BWT Racing Point F1 Team", car : "RP20", engine : "Mercedes", img : "https://d3qmgl49lqmtd9.cloudfront.net/live/tst18d2/racingpoint.png",top : false},
                    { name : "Alfa Romeo Racing Orlen", car : "C39", engine : "Ferrari", img : "https://d3qmgl49lqmtd9.cloudfront.net/live/tst18d2/alfaromeo.png",top : false},
                    { name : "Haas F1 Team", car : "VF-20", engine : "Ferrari", img : "https://d3qmgl49lqmtd9.cloudfront.net/live/tst18d2/haas.png",top : false},
                    { name : "ROKiT Williams Racing", car : "FW43", engine : "Mercedes", img : "https://d3qmgl49lqmtd9.cloudfront.net/live/tst18d2/williams.png",top : false},
                    { name : "W11 - Defending champion car 2019 ", car : "W10", engine : "Mercedes", img : "https://cdn-8.motorsport.com/images/vcl/K6xbRj2Q/s3/img992460015-1.png",top : true},
                    { name : "FW42 - Wooden Spoon 2019", car : "FW42", engine : "Mercedes", img : "https://cdn-9.motorsport.com/images/vcl/n0mZ4g2z/s3/img1339655169-1.png",top : false},
                ],
                diapos : [
                    { picture : "https://www.formula1.com/content/dam/fom-website/manual/Misc/2020/Car-launches/Mercedes/M226201.jpg" },
                    { picture: "https://autodius.com/wp-content/uploads/2020/02/ferrari-sf1000-f1.jpg"},
                    { picture : "https://img.sportauto.fr/news/2020/02/12/1546372/855e542dfddd26a815025d71-1920-1280.jpg"},
                    { picture : "https://www.formula1.com/content/dam/fom-website/manual/Misc/2020/Car-launches/McLaren/LandoNorris2020/2020_MCL35_LN4_3Q_NO_BAT_1.jpg"},
                    { picture : "https://img.sportauto.fr/news/2020/02/19/1546595/1fc973a1bd49bd2ef75caf8c-1920-1280.jpg"},
                    { picture : "https://img.sportauto.fr/news/2020/02/06/1546247/ddce8b5e8d7238a389063889-1920-1280.jpg"},
                    { picture : "https://img.autoplus.fr/picture/alfa_romeo/c39/1546486/Alfa_Romeo_C39_2020_165b9-1200-800.jpg"},
                    { picture : "https://www.formula1.com/content/dam/fom-website/manual/Misc/2020/Testing2020/Day1/GettyImages-1201880467.jpg"},
                    { picture : "https://img.autoplus.fr/news/2020/02/17/1546530/22391467fb64628f9db34246-1200-800.jpg"},
                    { picture : "https://img.autoplus.fr/news/2020/02/14/1546501/0430cd7aa33f0c7c34f79011-1200-800.jpg"},
                ],
                first : '',
                order : false,
                read : false,
                showButtons : 'hidden'
            }
        },
        computed : {
            // eslint-disable-next-line vue/return-in-computed-property
            topTeams() {
                if (this.order === true) {
                    return this.teams.filter(team =>  team.top)
                }
                else {
                    return this.teams.filter(team => !  team.top)
                }
            }
        },
        methods : {
            showOthers : function () {
                this.first = 'The Top Teams';
                this.order = true
            },
            showBests : function () {
                this.first = 'The Others';
                this.order = false
            },
            ShowMain : function () {
                this.read = true;
                this.first = 'The Top Teams';
                this.order = true;
                this.showButtons = 'visible'
            },
            DeleteMain : function () {
                this.read = false;
                this.first = '';
                this.order = false;
                this.showButtons = 'hidden'
            }
        }
    }
    


</script>

<style scoped>
    .card {
        height: 150px;
        width: 300px;
        background-color: #555;
        border-radius: 10px;
        text-align: center;
    }

    .name {
        font-weight: bold;
        margin-top: 5px;
        font-family: F1Font, sans-serif;
        font-size: 20px;
    }
    .engine {
        font-family: F1Font, sans-serif;
        margin-top: 5px;
        font-weight: bold;
    }
    .team {
        margin-top: 10px;
    }
    #hello {
        margin-top: 10px;
        display: block;
    }
    .subtitle {
        margin-top: 20px;
        font-family: F1Font,sans-serif;
        color: red;
        text-align: center;
    }
    .diapo {
        margin-top: 10px;
    }

    .buttons-component {
        margin-top: 10px;
        margin-left: 10px;
    }

    .buttons-main {
        text-align: center;
    }


</style>
