<template>
    <div>
        <header>
            <navbar></navbar>
        </header>

        <v-parallax id="bg" src="">
            <v-row align="center" justify="center">
                <v-col class="text-center" cols="12">
                    <h1 class = "display-3 font-weight-thin mx-auto">
                        Involvements
                    </h1>
                    <h4 class="subheading">Things I Do.</h4>
                </v-col>
            </v-row>
        </v-parallax>
        
        <v-divider></v-divider>

        <v-container class="mx-auto mb-12">
            <v-row >
                <v-col v-for="(org,i) in Orgs" :key="i" cols="12" >
                    <v-lazy
                        :options="{
                        threshold: .5
                        }"
                        min-height="200"
                        transition="fade-transition"
                    >
                        <v-hover v-slot:default="{ hover }">
                            <v-card :elevation="hover ? 12 : 2">
                                
                                <div class="d-flex flex-no-wrap">
                                    <v-avatar
                                        class="ma-3"
                                        size="125"
                                        tile
                                    >
                                        <v-img contain :src="org.logo"></v-img>
                                    </v-avatar>
                                    <div class="ml-12">
                                        <v-card-title class="headline"><a class="black--text" :href="org.link" v-text="org.title"></a></v-card-title>
                                        <v-card-subtitle v-text="org.subtitle"></v-card-subtitle>
                                        <v-card-text v-text="org.body"></v-card-text>
                                    </div>
                                </div>
                            </v-card>
                        </v-hover>
                    </v-lazy>
                    <v-divider class="mt-6"></v-divider>
                </v-col>
            </v-row>

        </v-container>
    </div>
</template>

<script>
import navbar from '~/components/navbar.vue';
import involvements from '~/assets/json/involvements.json';

export default {
    components: {
      navbar
    },
    data() {
        return {
            Orgs : involvements
        }
    }
}
</script>

<style scoped>
    #bg {
        background-image:linear-gradient(.125turn,#e66465, #9198e5);
    }
</style>