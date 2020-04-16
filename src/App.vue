<template>
  <div id="app">
    <SearchBar @filter='searchChange'/>
    <ItemList :items='this.config' :filter='this.filter' />
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
      config: [{ name: "" }],
      filter: ''
    };
  },
  methods: {
    searchChange: function (event) {
      this.filter = event
    }
  },
  mounted() {
    this.config = require('./assets/bl3items.json');
    this.config.sort(function (a, b) {
        a = a.name.toLowerCase()
        b = b.name.toLowerCase()
        return a > b ? 1 : b > a ? -1 : 0
      }
    )
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
