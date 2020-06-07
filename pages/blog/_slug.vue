<template>
  <div>
    <header>
      <navbar></navbar>
    </header>
    <v-parallax id="bg" src="">
        <v-row align="center" justify="start">
            <v-col cols="11" offset="1">
                <h1 class = "display-3 font-weight-thin mx-auto mx-12" v-text="post.title"></h1>
                <h4 class="subheading" v-text="post.subtitle"></h4>
            </v-col>
        </v-row>
    </v-parallax>

    <v-sheet class="d-flex" color="" height="120"></v-sheet>
  
    <v-container>
        <v-row align="center" justify="center">
          <v-col cols="8">
            <nuxt-content :document="post" class="title font-regular font-weight-regular"/>
          </v-col>
        </v-row>
    </v-container>

    <v-sheet class="d-flex" color="" height="120"></v-sheet>

  </div>
</template>
<script>
import navbar from '~/components/blognav.vue';

export default {
  async asyncData({$content, params}) {
        const post = await $content('blog',params.slug).fetch();
        return {post};
    },
    components: {
      navbar
    }
};
</script>
<style scoped>
  #bg {
        background-image:linear-gradient(.125turn,#6A4C93, #1982C4);
    }
</style>