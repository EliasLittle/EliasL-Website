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

        <v-row style="background:#F5F5F5" class="mx-n10">
            <!-- Albums Card -->
            <v-col sm="12" lg="4" class="ml-2">
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
            <v-col sm="12" lg="4" class="mx-n2">
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
            <v-col sm="12" lg="4" class="mr-2">
                <v-card outlined class="mx-auto">
                    <v-list-item-content class="mx-2">
                        <div class="overline mb-4">Mind</div>
                        <v-list-item-title class="headline mb-1">Some Thoughts</v-list-item-title>
                        <v-list-item-subtitle>Greyhound divisely hello coldly fonwderfully</v-list-item-subtitle>
                    </v-list-item-content>
                </v-card>
            </v-col>
        </v-row>

        <!-- Timeline -->
        <v-row justify="start">
            <v-col cols="8" left justify="start" flex>
                <v-timeline alignTop justify="start">
                    <v-timeline-item v-for="(item,i) in Timeline" :key="i" large right justify="start">
                        <template v-slot:icon>
                            <v-icon v-on="on" large>{{item.icon}}</v-icon>
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

        <!-- Other Links -->
        <v-row style="background:#F5F5F5">
            <p class="headline">Links</p>
            <v-col sm="12" lg="4">
                LinkedIn
            </v-col>
            <v-col sm="12" lg="4">
                Github
            </v-col>
            <v-col sm="12" lg="4">
                16Personalites
                https://www.16personalities.com/profiles/732c428cea46c
            </v-col>
            
        </v-row>

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
</style>