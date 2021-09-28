<template>
  <p>Hello, World! I'm testing here...</p>
  <p>{{this.slug}}</p>
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

  async asyncData({ params }) {
      const slug = params.slug // When calling /abc the slug will be "abc"
      //console.log("Slug: ", slug)
      //console.log("Link?: ", links[slug])
      return { slug }
  },
  
  /*mounted() {
    window.location.href = this.links[this.slug]; 
  },*/
};
</script>
