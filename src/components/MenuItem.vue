<template>
  <div class="single-item" v-bind:class="{'out-of-stock':item.out_of_stock}">
    <h3>{{ item.name }}</h3>
    <span>{{ item.price }}</span>
    <input type="checkbox" v-on:change="outOfStock">
    <p>{{  item.description }}</p>
    <button @click="$emit('remove-item', item.id)" class="remove">x</button>
  </div>
</template>

<script>
export default {
  name: "MenuIem",
  props: ["item"],
  methods: {
    outOfStock(){
      console.log("out of stock");
      this.item.out_of_stock = !this.item.out_of_stock
    }
  }
}
</script>

<style scoped>
  .single-item {
      display: inline-block;
      float: left;
      padding: 5px;
      margin: 10px;
      border: 1px solid #cccccc;
      width: 20%;
      cursor: pointer;
  }

  .out-of-stock {
      border: 1px solid #ff0000;
  }

  .remove {
      background-color: #ff0000;
      border: none;
      color: #ffffff;
      cursor: pointer;
  }
</style>