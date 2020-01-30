<template>
  <div class="todo-item" v-bind:class="{'is-complete':todo.completed}
  ">
    <p>
      <input type="checkbox" v-on:change="markComplete">
    {{todo.title}}
    <br>
    {{todo.description}}
    <br>
    <img :src="todo.image" :alt="todo.title">
    <br>
    €{{todo.price}}
    <br>
    {{todo.available}} gram available
    <button @click="$emit('del-todo', todo.id)"
     class="del">X</button>
    </p>
  </div>
</template>

<script>
export default {
  name: 'TodoItem',
  props: ['todo'],
  methods: {
    markComplete () {
      this.todo.completed = !this.todo.completed
    }

  }
}
</script>

<style scoped>

.todo-item{
  background: #f1f1f1;
  padding: 10px;
  border-bottom: 2px black solid;
}

.is-complete {
text-decoration: line-through;
}

.del {
background: red;
color: #fff;
border: none;
padding: 5px 9px;
border-radius: 50%;
cursor: pointer;
float: right;
}

</style>
