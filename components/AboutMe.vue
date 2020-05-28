<template>
  <div id="text" ><VueShowdown :markdown="fileContent" :options="{ emoji: true }"></VueShowdown></div>
</template>

<script>
import VueShowdown from "vue-showdown";
import MarkDownData from "!raw-loader!../assets/AboutMe";

export default {
  name: "App",
  props: {
    file: String
  },
  components: VueShowdown,
  data: function() {
    return {
      fileContent: null,
      fileToRender: "{{file}}",
      rawContent: null
    };
  },
  created: function() {
    //const fileToRender = `./assets/documentation/general/welcome.md`;
    //const rawContent = ""; // Read the file content using fileToRender
    // this.fileContent = "### marked(rawContent) should get executed";
    this.getContent();
  },
  methods: {
    getContent() {
      this.fileContent = MarkDownData;
    }
  }
};
</script>

<style scoped>
  #text{
      text-align: left;
      color:black;
      line-height: 24pt;
  }
</style>