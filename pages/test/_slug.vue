<template>
  <p>Hello, World! I'm testing here...</p>
</template>
<script>
import links from '~/assets/json/links.json';
export default {

  data() {
    return {
      links : links
    }
  },

  async asyncData({ params }) {
      const slug = params.slug // When calling /abc the slug will be "abc"
      return { slug }
  },
  
  mounted() {
    window.location.href = links[this.slug]; 
  },
};
</script>
