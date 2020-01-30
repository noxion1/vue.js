<template>
<div id="app">
  <Header />
  <AddTodo v-on:add-todo="addTodo" />
  <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo" />
</div>
</template>

<script>
import Header from '../components/layout/Header'
import Todos from '../components/Todos'
import AddTodo from '../components/AddTodo'
// import axios from 'axios'

export default {
  name: 'app',
  components: {
    Header,
    AddTodo,
    Todos
  },
  data () {
    return {
      todos: [
        {
          id: 1,
          title: 'Blue Berry Haze',
          description: 'Better then the real blue berries',
          image: 'https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fdutchseedsshop.com%2Fwp-content%2Fuploads%2F2016%2F07%2Fblueberry-haze-seeds.jpg&f=1&nofb=1',
          price: '11.50',
          available: '20',
          completed: false
        },
        {
          id: 2,
          title: 'Amnesia Haze',
          description: 'With earthy flavors of lemons and citrus, Amnesia Haze is a perfect strain to start your day with a smile. The uplifting, energetic buzz is one you won’t soon forget.',
          image: 'https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fwww.royalqueenseeds.com%2F115-1427-thickbox%2Famnesia-haze.jpg&f=1&nofb=1',
          price: '11.50',
          available: '20',
          completed: false
        },
        {
          id: 3,
          title: 'Pineapple Express',
          description: 'Pineapple Express combines the potent and flavorful forces of parent strains Trainwreck and Hawaiian. The smell is likened to fresh apple and mango, with a taste of pineapple, pine, and cedar.',
          image: 'https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fbuymyweedonline.ca%2Fwp-content%2Fuploads%2F2017%2F01%2F20170209_110103.jpg&f=1&nofb=1',
          price: '11.50',
          available: '20',
          completed: false
        }
      ]
    }
  },
  methods: {
    deleteTodo (id) {
      //  this.todo = this.todos.filter(todo => todo.id !== id)
      this.todos = this.todos.filter(todo => todo.id !== id)
      // .then(res => { this.todos = this.todos.filter(todo => todo.id !== id) })
      // .catch(err => console.log(err))
    },
    addTodo (newTodo) {
      this.todos = [...this.todos, newTodo]
      // .then(res => { this.todos = [...this.todos, res.data] })
      // .catch(err => console.log(err))
    }
  }
}

</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: sans-serif;
  line-height: 1.4;
}

.btn {
  display: inline-block;
  border: none;
  background: #555;
  color: #fff;
  padding: 7px 20px;
  cursor: pointer;
}

.btn:hover {
  background: #666;
}

img{
  width: 100px;
}
</style>
