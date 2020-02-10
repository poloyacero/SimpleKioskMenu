<template>
  <div id="app">
    <Header />
    <AddItem v-on:add-item="addItem"/>
    <Items v-bind:items="items" v-on:remove-item="removeItem"/>
  </div>
</template>

<script>
import Header from './components/layout/Header';
import Items from './components/Items';
import AddItem from './components/AddItem';
//import axios from 'axios';

export default {
  name: 'App',
  components: {
    Header,
    Items,
    AddItem
  },
  data() {
    return {
      items: []
    }
  },
  methods: {
    removeItem(id){
      // delete api here
      console.log(id);
      this.items = this.items.filter(item => item.id !== id);
    },
    addItem(newItem){
      // create or add api here
      console.log(newItem);
      this.items = [...this.items, newItem];
    }
    // to do update item
  },
  created(){
    // read or show api here
    console.log("Started");
    this.items = [
      {
          id: 1,
          name: "Apple",
          price: 5.00,
          out_of_stock: true,
          description: "Fresh Apples"
      },
      {
          id: 2,
          name: "Banana",
          price: 12.00,
          out_of_stock: false,
          description: "Fresh Bananas"
      },
      {
          id: 3,
          name: "Carrot",
          price: 15.00,
          out_of_stock: false,
          description: "Fresh Carrots"
      },
      {
          id: 4,
          name: "Dragon Fruit",
          price: 20.00,
          out_of_stock: false,
          description: "Fresh Dragon Fruit"
      }
    ]
  }
}
</script>

<style>

</style>
