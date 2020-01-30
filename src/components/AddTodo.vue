<template>
<div>
  <form @submit="addTodo">
    <input type="text" v-model="title" name="title" placeholder="Strain name">
    <input type="text" v-model="description" name="description" placeholder="description">
    <input type="text" v-model="image" name="image" placeholder="image url">
    <input type="text" v-model="price" name="price" placeholder="price per gram">
    <input type="text" v-model="available" name="available" placeholder="available">
    <input type="submit" value="Submit" class="btn">
  </form>
</div>
</template>

<script>
// import uuid from 'uuid';
export default {
  name: 'AddTodo',
  data () {
    return {
      title: '',
      description: '',
      image: '',
      price: '',
      available: ''
    }
  },
  methods: {
    addTodo (e) {
      e.preventDefault()
      const newTodo = {
        title: this.title,
        description: this.description,
        image: this.image,
        price: this.price,
        available: this.available,
        completed: false
      }
      // send up to parent
      this.$emit('add-todo', newTodo)

      this.title = ''

      this.description = ''

      this.image = ''

      this.price = ''

      this.available = ''
    }
  }
}
</script>

<style scoped>
form {
  display: flex;
}

input [type="text"] {
  flex: 10;
  padding: 5px;
}

input [type="submit"] {
  flex: 2;
}
</style>
