<template>
  <div class="item">
    <div> {{item.name}} </div>
  </div>
</template>

<script>
export default {
  name: 'Item',
  props: {
    item: Object
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.item {
  font-size: 24px;
  text-align: left;
  padding-bottom: 6px;
}

</style>
