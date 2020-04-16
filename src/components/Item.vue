<template>
  <div class="item">
    <span> {{item.name}} </span>
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

</style>
