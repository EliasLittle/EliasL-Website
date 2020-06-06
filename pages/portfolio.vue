<template>
    <div>
        <header>
            <navbar></navbar>
        </header>

        <v-parallax id="bg" src="">
            <v-row align="center" justify="center">
                <v-col class="text-center" cols="12">
                    <h1 class = "display-3 font-weight-thin mx-auto">
                        Portfolio
                    </h1>
                    <h4 class="subheading">Things I build.</h4>
                </v-col>
            </v-row>
        </v-parallax>

        <v-divider></v-divider>

        <v-container class="mx-auto mb-12">
            <v-row >
                <v-col v-for="(proj,i) in Projects" :key="i" cols="12" >
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
                                        <v-img contain :src="proj.logo"></v-img>
                                    </v-avatar>
                                    <div class="ml-12">
                                        <v-card-title class="headline"><a class="black--text" :href="proj.link" v-text="proj.title"></a></v-card-title>
                                        <v-card-subtitle v-text="proj.subtitle"></v-card-subtitle>
                                        <v-card-text v-text="proj.body"></v-card-text>
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
import projects from '~/assets/json/portfolio.json';

export default {
    data() {
        return {
            Projects : projects
        }
    },
    components: {
      navbar
    }
}
</script>

<style scoped>
    #bg {
        background-image:linear-gradient(-.125turn,#9198e5,#61E786);
    }
</style>