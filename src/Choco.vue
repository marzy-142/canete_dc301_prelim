<template>
  <div>
    <h1>Available Gourmet Chocolates</h1>
    <ul>
      <li v-for="(item, index) in items" :key="index">
        <input type="checkbox" v-model="item.selected" /> {{ item.name }} ➜ ₱{{ item.price }}
      </li>
    </ul>
    <br />
    <br />
    <h2 class="total" v-if="total === 0">Please select at least one item to see the total.</h2>
    <h2 v-else>Total: ₱{{ total }}</h2>
  </div>
</template>

<script>
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
