<template>
  <div class="itemlist">
    <Item v-for='(item) in this.items' v-bind:key='item.id' :item='item' :itemfilter='filter'/>
  </div>
</template>

<script>
import Item from "./Item.vue";

export default {
  name: 'ItemList',
  components: {
    Item
  },
  props: {
    items: Array,
    filter: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.itemlist {
  overflow-y: scroll;
  max-height: 100vh;
  margin-left: 16px;
  margin-right: 10px;
}

</style>
