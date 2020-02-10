<template>
  <div>
    <div v-bind:key="item.id" v-for="item in items">
      <MenuItem v-bind:item="item" v-on:remove-item="$emit('remove-item', item.id)"/>
    </div>
  </div>
</template>

<script>
import MenuItem from './MenuItem.vue'

export default {
  name: "Items",
  components: {
    MenuItem
  },
  props: ["items"]
}
</script>

<style scoped>

</style>>