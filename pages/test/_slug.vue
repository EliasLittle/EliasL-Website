<template>
  <p>Hello, World! I'm testing here...</p>
  <p>{{ this.id }}</p>
  <p>{{ this.lnk }}</p>
</template>
<script>
//import links from '~/assets/json/links.json';
//console.log(links["youtube"]);
export default {

  /*data() {
    return {
      links : links
    }
  },*/

  async asyncData({$content, params }) {
      const lnks = await $content('links.json').fetch();
      const id = params.slug; // When calling /abc the slug will be "abc
      const lnk = lnks[id];
      //console.log("Slug: ", slug)
      //console.log("Link?: ", links[slug])
      return { id, lnk };
  },
  
  /*mounted() {
    window.location.href = this.links[this.slug]; 
  },*/
};
</script>
