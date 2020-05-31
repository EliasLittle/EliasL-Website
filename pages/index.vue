<template>
    
  <div>
    
    <header>
      <navbar></navbar>
    </header>

    <v-parallax src="https://images.squarespace-cdn.com/content/v1/54c1f4dbe4b01ba65f531399/1560028168030-PJGGGNCKV4ZJDX1NSK8Z/ke17ZwdGBToddI8pDm48kCPztTQZpDiZMOuuCfUxiyx7gQa3H78H3Y0txjaiv_0fDoOvxcdMmMKkDsyUqMSsMWxHk725yiiHCCLfrh8O1z5QPOohDIaIeljMHgDF5CVlOqpeNLcJ80NK65_fV7S1UYlQ-m0oNUh_9buvyC-f1CSdhG_dNlqULB2ZTz-ses64A-QPhXXvNcU0N8wN7BGx0g/Beautiful-Sunset-Lake-Austin-Texas-Aerial-Drone-Photo.jpg?format=2500w">
        <div class = "display-4 font-italic font-weight-light mx-auto">
            Elias Joaquín Little
        </div>
    </v-parallax>

    <div class="mx-10 mb-10">
        <v-row>
            
            <v-col sm="12" lg="3">
                <v-container class=".d-md-none .d-lg-flex">
                    <v-img src="img/eliasHeadshot.jpg"/>
                </v-container>
            </v-col>
            

            <v-col sm="12" lg="9">
                <v-container>
                    <nuxt-content :document="aboutMe" />
                </v-container>
            </v-col>
        </v-row>

        <v-divider></v-divider>

        <v-row>
            <v-col sm="12" lg="4">
                <v-card outlined class="mx-auto">
                    <v-list-item-content class="mx-2">
                        <div class="overline mb-4">Ears</div>
                        <v-list-item-title class="headline mb-1">Music</v-list-item-title>
                        <v-list-item-subtitle>Some Of My Favorite Songs and Albums</v-list-item-subtitle>
                    </v-list-item-content>

                    <v-list two-line shaped>
                        <v-list-item-group v-model="selected" multiple active-class="blue--text">
                            <v-list-item>
                                <v-list-item-content>
                                    <v-list-item-title><a class="black--text" href="https://open.spotify.com/album/4SxFsOO0h4Nz3lFJuysKq5?si=kwnbbWXcQdalx6lJrE4B8Q">For Emma Forever Ago</a></v-list-item-title>
                                    <v-list-item-subtitle>Bon Iver</v-list-item-subtitle>
                                    <!--<iframe src="https://open.spotify.com/embed/album/4SxFsOO0h4Nz3lFJuysKq5" width="300" height="380" frameborder="0" allowtransparency="true" allow="encrypted-media"></iframe>-->
                                </v-list-item-content>
                            </v-list-item>

                            <v-list-item>
                                <v-list-item-content>
                                    <v-list-item-title><a class="black--text" href="https://open.spotify.com/album/4NZWRpoMuXaHU7csTjWdB5?si=7yFJvu_4S9iFtyT_3CMf6Q">Skin</a></v-list-item-title>
                                    <v-list-item-subtitle>Flume</v-list-item-subtitle>
                                </v-list-item-content>
                            </v-list-item>

                            <v-list-item>
                                <v-list-item-content>
                                    <v-list-item-title><a class="black--text" href="https://open.spotify.com/album/7BKGTpCWDwTCeHnlLFcfLJ?si=zF62WnYrSS2tBEWEwo2xXA">Lewis Del Mar</a></v-list-item-title>
                                    <v-list-item-subtitle>Lewis Del Mar</v-list-item-subtitle>
                                </v-list-item-content>
                            </v-list-item>

                            <v-list-item>
                                <v-list-item-content>
                                    <v-list-item-title><a class="black--text" href="https://open.spotify.com/album/4Carzsnpd6yvuHZ49I0oz8?si=HB4HmYuxRhKfo8ywr_tOMA">"Awaken, My Love!"</a></v-list-item-title>
                                    <v-list-item-subtitle>Childish Gambino</v-list-item-subtitle>
                                </v-list-item-content>
                            </v-list-item>
                        </v-list-item-group>
                    </v-list>
                </v-card>
            </v-col>

            <v-col sm="12" lg="4">
                <v-card outlined class="mx-auto">
                    <v-list-item-content class="mx-2">
                        <div class="overline mb-4">Eyes</div>
                        <v-list-item-title class="headline mb-1">Reading List</v-list-item-title>
                        <v-list-item-subtitle>Books I'm currently reading or have recently read.</v-list-item-subtitle>
                    </v-list-item-content>

                    <v-list two-line shaped>
                        <v-list-item-group v-model="selected" multiple active-class="blue--text">
                            <v-list-item>
                                <v-list-item-content>
                                    <v-list-item-title><a class="black--text" href="https://www.amazon.com/gp/product/1250251052/ref=as_li_tl?ie=UTF8&camp=1789&creative=9325&creativeASIN=1250251052&linkCode=as2&tag=eliaslwebsite-20&linkId=ebfcf646356e2fbc1b067931faedfebc">Territory of Light</a></v-list-item-title>
                                    <v-list-item-subtitle class="text--primary">A Novel</v-list-item-subtitle>
                                    <v-list-item-subtitle>Yuko Tsushima </v-list-item-subtitle>
                                </v-list-item-content>
                            </v-list-item>

                            <v-list-item>
                                <v-list-item-content>
                                    <v-list-item-title><a class="black--text" href="https://www.amazon.com/gp/product/0399592091/ref=as_li_tl?ie=UTF8&camp=1789&creative=9325&creativeASIN=0399592091&linkCode=as2&tag=eliaslwebsite-20&linkId=5a143383f4d1a41148a0ad35a7698716">The Ride of A Lifetime</a></v-list-item-title>
                                    <v-list-item-subtitle class="text--primary">Lessons Learned From 15 Years As CEO Of The Walt Disney Company</v-list-item-subtitle>
                                    <v-list-item-subtitle>Robert Iger</v-list-item-subtitle>
                                </v-list-item-content>
                            </v-list-item>

                            <v-list-item>
                                <v-list-item-content>
                                    <v-list-item-title><a class="black--text" href="https://www.amazon.com/gp/product/0465094279/ref=as_li_tl?ie=UTF8&camp=1789&creative=9325&creativeASIN=0465094279&linkCode=as2&tag=eliaslwebsite-20&linkId=b33cbf68b4ad24a88bd4540bedff37e4">The Master Algorithm</a></v-list-item-title>
                                    <v-list-item-subtitle class="text--primary">How The Quest For The Ultimate Learning Machine Will Remake Our World</v-list-item-subtitle>
                                    <v-list-item-subtitle>Pedro Domingos</v-list-item-subtitle>
                                </v-list-item-content>
                            </v-list-item>

                            <v-list-item>
                                <v-list-item-content>
                                    <v-list-item-title><a class="black--text" href="https://www.amazon.com/gp/product/0393351599/ref=as_li_tl?ie=UTF8&camp=1789&creative=9325&creativeASIN=0393351599&linkCode=as2&tag=eliaslwebsite-20&linkId=8217e73101f8a3d899c9fa394bf20a87">Flash Boys</a></v-list-item-title>
                                    <v-list-item-subtitle class="text--primary">A Wall Street Revolt</v-list-item-subtitle>
                                    <v-list-item-subtitle>Michael Lewis</v-list-item-subtitle>
                                </v-list-item-content>
                            </v-list-item>
                        </v-list-item-group>
                    </v-list>
                </v-card>
            </v-col>

            <v-col sm="12" lg="4">
                <v-card outlined class="mx-auto">
                    <v-list-item-content class="mx-2">
                        <div class="overline mb-4">Mind</div>
                        <v-list-item-title class="headline mb-1">Some Thoughts</v-list-item-title>
                        <v-list-item-subtitle>Greyhound divisely hello coldly fonwderfully</v-list-item-subtitle>
                    </v-list-item-content>
                </v-card>
            </v-col>
        </v-row>
    </div>

  </div>
</template>

<script>
import navbar from '~/components/navbar.vue';
import albums from '~/assets/json/albums.json';

export default {
    data () {
        return {
            Albums: albums
        }
    },
    components: {
      navbar,
    },
    async asyncData({$content}) {
        const aboutMe = await $content('AboutMe').fetch();
        return {aboutMe};
    },
    computed: {
      aboutme() {
        return aboutme
      }
    }
}
</script>
