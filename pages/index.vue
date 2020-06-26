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
                </v-container>
            </v-col>
        </v-row>

        <!-- hobby cards -->
        <v-row style="background:#F5F5F5" class="mx-n10 px-5 py-2">
            <!-- Albums Card -->
            <v-col sm="12" lg="4" class="">
                <v-card outlined class="mx-auto">

                    <v-list-item-content class="mx-2">
                        <div class="overline mb-4">Ears</div>
                        <v-list-item-title class="headline mb-1">Music</v-list-item-title>
                        <v-list-item-subtitle>Some of my favorite albums</v-list-item-subtitle>
                    </v-list-item-content>

                    
                    <v-list two-line shaped>

                        <v-list-group 
                        v-for="album in AlbumList" 
                        :key="album.title"
                        multiple 
                        no-action
                        active-class="blue--text">
                            <template v-slot:activator>
                                <v-list-item>
                                    <v-list-item-content>
                                        <v-list-item-title>{{album.title}}</v-list-item-title>
                                        <v-list-item-subtitle>{{album.artist}}</v-list-item-subtitle>
                                    </v-list-item-content>
                                </v-list-item>
                            </template>
                            <v-list-item>
                                <v-list-item-content>
                                    <iframe :src="album.embed" width="300" height="380" frameborder="0" allowtransparency="true" allow="encrypted-media"></iframe>
                                </v-list-item-content>
                            </v-list-item>
                        </v-list-group>

                    </v-list>

                </v-card>
            </v-col>
            <!-- Books Card -->
            <v-col sm="12" lg="4" class="">
                <v-card outlined class="mx-auto">
                    <v-list-item-content class="mx-2">
                        <div class="overline mb-4">Eyes</div>
                        <v-list-item-title class="headline mb-1">Reading List</v-list-item-title>
                        <v-list-item-subtitle>Books I'm currently reading or have recently read</v-list-item-subtitle>
                    </v-list-item-content>

                    <v-list two-line shaped>

                        <v-list-group 
                        v-for="book in BookList" 
                        :key="book.title"
                        multiple 
                        no-action
                        active-class="blue--text">
                            <template v-slot:activator>
                                <v-list-item>
                                    <v-list-item-content>
                                        <v-list-item-title>{{book.title}}</v-list-item-title>
                                        <v-list-item-subtitle class="text--primary d-none d-md-flex d-lg-none">{{book.subtitle}}</v-list-item-subtitle>
                                        <v-list-item-subtitle >{{book.author}}</v-list-item-subtitle>
                                    </v-list-item-content>
                                </v-list-item>
                            </template>
                            <v-list-item>
                                <v-list-item-content>
                                    <v-row>
                                        <v-col sm="3" lg="6" class="mx-2">
                                            <a target="_blank" :href="book.urlone"><img border="0" :src="book.urltwo" ></a><img src="book.urlthree" width="1" height="1" border="0" alt="" style="border:none !important; margin:0px !important;" />
                                        </v-col>
                                        <!-- Future addition: Review link
                                        <v-col sm="8" md="4" lg="6" class="mx-2">
                                            <v-sheet color="blue lighten-3" height="250" class="float-right d-lg-flex">{{book.review}}</v-sheet>
                                        </v-col>
                                        -->
                                    </v-row>
                                </v-list-item-content>
                            </v-list-item>
                        </v-list-group>

                    </v-list>

                </v-card>
            </v-col>

            <!-- Thoughts Card -->
            <v-col sm="12" lg="4" class="">
                <v-card outlined class="mx-auto">
                    <v-list-item-content class="mx-2">
                        <div class="overline mb-4">Mind</div>
                        <v-list-item-title class="headline mb-1">Some Thoughts</v-list-item-title>
                        <v-list-item-subtitle>Greyhound divisely hello coldly fonwderfully</v-list-item-subtitle>
                    </v-list-item-content>
                </v-card>
            </v-col>
        </v-row>

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

        <!-- Other Links -->
        <div id="profiles">
            <v-row class="pt-8 px-10 mx-n10">
                <p class="display-1 font-weight-bold">Profiles</p>
            </v-row>
            <v-row style="background:#F5F5F5" class="mx-n10 px-5 py-2">
                <v-col sm="12" lg="4" v-for="profile in Profiles" :key="profile.name">
                    <v-hover v-slot:default="{ hover }">
                        <v-card :elevation="hover ? 12 : 2" class="transition-swing" :color="profile.color" :href="profile.link" height="200">
                            <v-list-item three-line>
                                <v-list-item-content class="white--text">
                                    <div class="overline mb-2">{{profile.overline}}</div>
                                    <v-list-item-title class="headline mb-1" v-text="profile.name"></v-list-item-title>
                                    <v-list-item-text class="body-2 white--text" v-text="profile.body"></v-list-item-text>
                                </v-list-item-content>
                                <v-list-item-avatar tile size="60"><v-img contain :src="profile.logo"/></v-list-item-avatar>
                            </v-list-item>
                        </v-card>
                    </v-hover>
                </v-col>
            </v-row>
        </div>

        <v-sheet class="d-flex" height="120"></v-sheet>
    </div>

  </div>
</template>

<script>
import navbar from '~/components/navbar.vue';
import albumlist from '~/assets/json/albums.json';
import booklist from '~/assets/json/books.json';

export default {
    data () {
        return {
            AlbumList: albumlist,
            BookList: booklist,
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
            ],
            Profiles : [
                {
                    "name":"LinkedIn",
                    "link":"https://www.linkedin.com/in/elias-little/",
                    "logo":"img/linkedin.svg",
                    "color":"#0576B5",
                    "overline":"Business",
                    "body":"Come say 'hi' and see what I've been up to professionally. Maybe we can work together on something!"
                },
                {
                    "name":"GitHub",
                    "link":"https://github.com/EliasLittle",
                    "logo":"img/github.svg",
                    "color":"#7042C1",
                    "overline":"Code",
                    "body":"Take a peek at some of my code. Some of it's good, some of it's quick, most of it is unfinished (I'll get around to it eventually)"
                },
                {
                    "name":"16 Personalities",
                    "link":"https://www.16personalities.com/profiles/732c428cea46c",
                    "logo":"img/16p.svg",
                    "color":"#3D9294",
                    "overline":"Personality",
                    "body":"Get to know me before we even meet. I promise there won't be a test though when we do, so don't be pressured to study."
                }
            ]
        }
    },
    components: {
      navbar
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