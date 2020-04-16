<template>
  <div class='item' v-show='filtered'>
    <div class='name'> {{item.name}} </div>
    <div class='redtext'> {{item.redtext}} </div>
    <div :class='{ tier1: tier1, tier2: tier2 }' class='tierbanner'></div>
    <div class='details'>
      <div class='type'> <span v-if='topTier'>Tier</span> {{item.tier}} {{item.brand}} <span class='bold'>{{item.type}}</span></div>
      <div class='summary'>{{item.summary}}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Item',
  props: {
    item: Object,
    itemfilter: String
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
    },
    filtered: function() {
      return (this.item.name.toLowerCase().includes(this.itemfilter))
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.item {
  padding-bottom: 16px;
}

.name {
  font-size: 28px;
  text-align: left;
}

.redtext {
  font-size: 16px;
  text-align: left;
  color: red;
  margin-bottom: 4px;
  font-style:italic;
}

.type {
  font-size: 16px;
  text-align: left;
}

.summary {
  font-size: 16px;
  text-align: left;
  margin-top: 6px;
}

.details {
  color: grey;
}

.tierbanner {
  width: 95%;
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
