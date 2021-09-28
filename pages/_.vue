<template>
</template>
<script>
import links from "~/content/links.json";
//import links from '~/assets/json/links.json';
//console.log(links["youtube"]);
export default {

  /*data() {
    return {
      links : links
    }
  },*/

  async asyncData({ params }) {
      const id = params.pathMatch; 
      // pathMatch allows any path over a single slug, 
      // Thus both cal/school and cal/personal can match to different things
      const link = (id in links) ? links[id] : "/undefined";
      return { id, link };
  },
  
  mounted() {
    window.location.href = this.link; 
  },
};
</script>
