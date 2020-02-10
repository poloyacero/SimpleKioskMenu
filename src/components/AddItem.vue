<template>
  <div>
    <form @submit="addItem">
      <input type="text" name="name" v-model="name" placeholder="Add Menu Item" />
      <input type="text" name="price" v-model="price" placeholder="Add Item Price" />
      <input type="text" name="description" v-model="description" placeholder="Add Item Description" />
      <input type="submit" value="Submit" />
    </form>
  </div>
</template>

<script>
import uuid from 'uuid';
export default {
  name: "AddItem",
  data() {
    return {
      name: '',
      price: '',
      description: ''
    }
  },
  methods: {
    addItem(e){
      e.preventDefault();
      const newItem = {
        id: uuid.v4(),
        name: this.name,
        price: this.price,
        description: this.description,
        out_of_stock: false
      }
      // send up to parent
      this.$emit('add-item', newItem);
      // clear the form after submitting
      this.clearForm(e);
    },
    clearForm(e){
        e.target.reset();
    }
  }
}
</script>

<style scoped>

</style>>