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

  async asyncData({$content, params }) {
      //const lnks = await $content('links.json').fetch();
      const id = params.slug; // When calling /abc the slug will be "abc
      const lnk = links[id];
      //console.log("Slug: ", slug)
      //console.log("Link?: ", links[slug])
      return { id, link };
  },
  
  mounted() {
    window.location.href = this.link; 
  },
};
</script>
