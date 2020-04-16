<template>
  <div id="app">
    <SearchBar />
    <ItemList :items='this.config' />
  </div>
</template>

<script>
import SearchBar from "./components/SearchBar.vue";
import ItemList from "./components/ItemList.vue";

export default {
  name: "App",
  components: {
    SearchBar,
    ItemList
  },
  data: function() {
    return {
      // init the json config object with an empty [0] because I reference it in the template
      // can be config: {} once I remove that hard reference
      config: [{ name: "" }]
    };
  },
  mounted() {
    this.config = require('./assets/bl3items.json');
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 20px;
}
</style>
