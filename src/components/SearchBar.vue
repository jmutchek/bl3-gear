<template>
  <div class="search">
    <input v-model='searchterm' :autofocus="true"/>
  </div>
</template>

<script>
export default {
  name: 'SearchBar',
  props: {
  },
  data: function () {
    return {
      searchterm: ''
    }
  },
  watch: {
    searchterm: function(val) {
      this.$emit('filter', val)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.search {
  margin: 20px; 
}

input {
  font-size: 30px;
  width: 90%;
}

</style>
