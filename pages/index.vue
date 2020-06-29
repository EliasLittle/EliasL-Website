<template>

  <div>

    <header>
      <navbar></navbar>
    </header>

    <!-- Austin Image: https://images.squarespace-cdn.com/content/v1/54c1f4dbe4b01ba65f531399/1560028168030-PJGGGNCKV4ZJDX1NSK8Z/ke17ZwdGBToddI8pDm48kCPztTQZpDiZMOuuCfUxiyx7gQa3H78H3Y0txjaiv_0fDoOvxcdMmMKkDsyUqMSsMWxHk725yiiHCCLfrh8O1z5QPOohDIaIeljMHgDF5CVlOqpeNLcJ80NK65_fV7S1UYlQ-m0oNUh_9buvyC-f1CSdhG_dNlqULB2ZTz-ses64A-QPhXXvNcU0N8wN7BGx0g/Beautiful-Sunset-Lake-Austin-Texas-Aerial-Drone-Photo.jpg?format=2500w-->
    <v-parallax id="bg" src="">
        <div class = "display-4 font-italic font-weight-thin mx-auto">
            Elias Joaquín Little
        </div>
        <div class = "text-h5 white--text font-weight-bold mt-4 mx-auto" >
            Aspiring Polymath
            <!-- <vue-typer :text='[ "Aspring Polymath", "Full-time Student"]' erase-style="backspace"></vue-typer> -->
        </div>
    </v-parallax>

    <v-sheet height="50"></v-sheet>

    <div class="mx-10 mb-12">
        <v-row>

            <v-col xs="0" lg="3" class="d-none d-lg-flex">
                <v-container>
                    <v-img src="img/eliasHeadshot.jpg"/>
                </v-container>
            </v-col>


            <v-col xs="12" sm="12" lg="9">
                <v-container>
                    <nuxt-content :document="aboutMe" />
                    <v-lazy>
                        <v-sparkline :smooth="16" 
                        :gradient="['#2B59C3', '#D56AA0']" 
                        gradient-direction="left" 
                        :value="[1,1,2,3,5,8,13,21,34,55,89,144]" 
                        line-width="2" height="30" 
                        auto-draw stroke-linecap="round">
                        </v-sparkline>
                    </v-lazy>
                </v-container>
            </v-col>
        </v-row>

        <!-- Hobby Cards -->
        <div id="HobbyCards">
            <HobbyCards></HobbyCards>
        </div>

        <!-- ads -->
        <v-row>
            <!-- <adsbygoogle> Hello Ad</adsbygoogle> -->
        </v-row>

        <!-- Timeline 
        <v-row justify="start">
            <v-col cols="8" left justify="start" flex>
                <v-timeline alignTop justify="start">
                    <v-timeline-item v-for="(item,i) in Timeline" :key="i" large right justify="start">
                        <template v-slot:icon>
                            <v-icon large>{{item.icon}}</v-icon>
                        </template>
                        <template v-slot:opposite>
                            <span>{{item.date}}</span>
                        </template>
                        <v-card class="elevation-2">
                            <v-card-title class="headline">{{item.title}}</v-card-title>
                            <v-card-text>{{item.body}}</v-card-text>
                        </v-card>
                    </v-timeline-item>
                </v-timeline>
            </v-col>
        </v-row>
        -->

        <!-- Other Profiles -->
        <Profiles></Profiles>

        <v-sheet class="d-flex" height="120"></v-sheet>
    </div>

  </div>
</template>

<script>
import navbar from '~/components/navbar.vue';
import HobbyCards from '~/components/HobbyCards.vue';
import Profiles from '~/components/Profiles.vue';

export default {
    data () {
        return {
            Timeline : [
                {
                    "title":"Born",
                    "icon":"mdi-history",
                    "location":"Grass Valley, California",
                    "date":"April 26, 2001",
                    "body":"The adventure begins"
                },
                {
                    "title":"The Big Move",
                    "icon":"mdi-home",
                    "location":"Grass Valley -> Austin, TX",
                    "date":"Winter, 2003",
                    "body":"Move to my childhood home, and the city I was raised in"
                }
            ]
        }
    },
    components: {
      navbar,
      HobbyCards,
      Profiles
    },
    async asyncData({$content}) {
        const aboutMe = await $content('AboutMe').fetch();
        return {aboutMe};
    }
}

</script>

<style scoped>
    #bg {
        background-image:linear-gradient(.125turn,#2B59C3, #D56AA0);
    }
    .v-card {
        transition: ease-in-out opasity .4s ;
    }
    .vue-typer .custom.char.typed {
        color: #FFFFFF;
    }
    .particle-wrap {
        height: 30em;
    }
</style>
