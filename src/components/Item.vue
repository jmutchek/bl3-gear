<template>
  <div class='item'>
    <div class='name'> {{item.name}} </div>
    <div class='redtext'> {{item.redtext}} </div>
    <div :class='{ tier1: tier1, tier2: tier2 }' class='tierbanner'></div>
    <div class='details'>
      <div class='type'> <span v-if='topTier'>Tier</span> {{item.tier}} {{item.brand}} <span class='bold'>{{item.type}}</span></div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Item',
  props: {
    item: Object
  },
  computed: {
    topTier: function() {
      return (this.item.tier > 0)
    },
    tier1: function() {
      return (this.item.tier == 1)
    },
    tier2: function() {
      return (this.item.tier == 2)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.item {
  padding-bottom: 12px;
}

.name {
  font-size: 24px;
  text-align: left;
}

.redtext {
  font-size: 12px;
  text-align: left;
  color: red;
  margin-bottom: 4px;
  font-style:italic;
}

.type {
  font-size: 12px;
  text-align: left;
}

.details {
  color: grey;
}

.tier1 {
  background-color: goldenrod;
  height: 6px;
  margin-bottom: 4px;
}

.tier2 {
  background-color: silver;
  height: 6px;
  margin-bottom: 4px;
}

.bold {
  font-weight: bold;
}

</style>
