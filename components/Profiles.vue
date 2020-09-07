<template>
    <div id="profiles">
        <v-row class="px-10 mx-n10 mt-5 pt-5">
            <p class="display-1 font-weight-bold">Profiles</p>
        </v-row>
        <v-lazy>
            <v-sparkline :smooth="16"
            :gradient="['#0576B5', '#7042C1','#3D9294']"
            gradient-direction="left"
            :value="[1,1]"
            line-width="1.5" height="22"
            auto-draw stroke-linecap="round"
            class="ma-md-n4 mx-md-n10 mb-5 pb-5 pt-n5 mt-n5">
            </v-sparkline>
        </v-lazy>
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
        <v-lazy>
            <v-sparkline :smooth="16"
            :gradient="['#0576B5', '#7042C1','#3D9294']"
            gradient-direction="left"
            :value="[1,1]"
            line-width="1.5" height="22"
            auto-draw stroke-linecap="round"
            class="ma-md-n4 mx-md-n10 my-4 ">
            </v-sparkline>
        </v-lazy>
    </div>
</template>

<script>
export default {
    data () {
        return {
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
    }
}
</script>
