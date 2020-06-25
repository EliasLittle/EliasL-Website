<template>
    <div>
        <header>
            <navbar></navbar>
        </header>

        <v-parallax id="bg" src="">
            <v-row align="center" justify="center">
                <v-col class="text-center" cols="12">
                    <h1 class = "display-3 font-weight-thin mx-auto">
                        Stochastic Theories
                    </h1>
                    <h4 class="subheading">A collection of my random thoughts and theories.</h4>
                </v-col>
            </v-row>
        </v-parallax>
        <v-row align="center">
            <v-divider class="ma-6" dashed ></v-divider>
        </v-row>

        <v-container class="mx-auto mb-12">
            <v-row >
                <v-col v-for="(post,i) in posts" :key="i" cols="12" >
                    <v-lazy
                        :options="{
                        threshold: .5
                        }"
                        min-height="200"
                        transition="fade-transition"
                    >
                        <v-hover v-slot:default="{ hover }">
                            <v-card :elevation="hover ? 12 : 2" :to="post.path">
                                
                                <div class="d-flex flex-no-wrap">
                                    <div class="ml-12">
                                        <v-card-title tag="li" class="headline font-weight-light" v-text="post.title"></v-card-title>
                                        <v-card-subtitle v-text="post.subtitle"></v-card-subtitle>
                                        <v-card-text v-text="post.description"></v-card-text>
                                    </div>
                                </div>
                            </v-card>
                        </v-hover>
                    </v-lazy>
                    <v-divider class="mt-6"></v-divider>
                </v-col>
            </v-row>
            <v-row>
                <adsbygoogle />
            </v-row>

        </v-container>

        
    </div>
</template>

<script>
import navbar from '~/components/navbar.vue';

export default {
    async asyncData({ $content, params}) {
        const posts = await $content("blog").sortBy("createdAt","desc").fetch();
        console.log("posts", posts);
        return { posts };
    },
    components: {
      navbar
    },
    data() {
        return {
            
        }
    }
}
</script>

<style scoped>
    #bg {
        background-image:linear-gradient(.125turn,#6A4C93, #1982C4);
    }
</style>