<template>
<div>
  <form @submit="addWiet">
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
  name: 'AddWiet',
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
    addWiet (e) {
      e.preventDefault()
      const newWiet = {
        title: this.title,
        description: this.description,
        image: this.image,
        price: this.price,
        available: this.available,
        completed: false
      }
      // send up to parent
      this.$emit('add-wiet', newWiet)

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
  flex: 16;
  padding: 5px;
}

input [type="submit"] {
  flex: 2;
}

</style>
