<template>
  <center>
  <div class="wiet-item" v-bind:class="{'is-complete':wiet.completed}">
    <p class="grootenrood">
      Uitverkocht
      <input type="checkbox" v-on:change="markComplete">
      </p>
      <br>
      <br>
      <h3>
    {{wiet.title}}
    <br>
  </h3>
    <div class="wordWrap">{{wiet.description}}</div>
    <br>
    <p>
    <img :src="wiet.image" :alt="wiet.title">
    </p>
    <br>
    <p>
    Prijs per gram: €{{wiet.price}}
  </p>
  <p>
    Gram in stock: {{wiet.available}}g
    <br>
    <button @click="$emit('del-wiet', wiet.id)" class="del">Remove Item</button>
    </p>
  </div>
</center>
</template>

<script>
export default {
  name: 'WietItem',
  props: ['wiet'],
  methods: {
    markComplete () {
      this.wiet.completed = !this.wiet.completed
    }

  }
}
</script>

<style scoped>

.wiet-item{
  color: black;
  background: #cff660;
  padding: 30px;
  border-bottom: 2px black solid;
  border-left: 2px black solid;
  border-right: 2px black solid;
  width: 600px;
}

.is-complete {
text-decoration: line-through;
background-color: #f4ba2e;
}

.is-complete .grootenrood {
  position: relative;
text-decoration: none;
color: red;
background-color: #f4ba2e;
}

.del {
background: red;
color: #fff;
border: none;
padding: 5px 9px;
border-radius: 1%;
cursor: pointer;
float: right;
}

</style>
