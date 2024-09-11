<template>
  <div id="app">
    <ItemList :items="items" />
  </div>
</template>

<script>
import ItemList from './components/ItemList.vue'

export default {
  data() {
    return {
      items: [
        { id: 1, name: 'Ghirardelli', price: 1200, selected: false },
        { id: 2, name: 'Compartés', price: 500, selected: false },
        { id: 3, name: 'Lindt', price: 1250, selected: false },
        { id: 4, name: "Tony's Chocolonely", price: 2000, selected: false }
      ]
    }
  }
}
</script>

<style>
#app {
  font-family: Arial, Helvetica, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #333;
  margin-top: 60px;
  background-color: #eef2f5;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: flex-start;
  padding: 20px;
}
</style>
