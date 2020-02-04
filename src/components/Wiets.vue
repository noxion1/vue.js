<template>
  <div>
    <div v-bind:key="wiet.id" v-for="wiet in wiets">
    <WietItem v-bind:wiet="wiet" v-on:del-wiet="$emit('del-wiet', wiet.id)" />
    </div>
  </div>
</template>

<script>
import WietItem from './WietItem.vue'

export default {
  name: 'Wiets',
  components: {
    WietItem
  },
  props: ['wiets']
}
</script>

<style scoped>
</style>
