<template>
  <div class="product-list">
    <h2>Product List</h2>
    <div class="products-container">
      <ProductItem
        v-for="product in products"
        :key="product.id"
        :product="product"
        @add-to-cart="handleAddToCart"
      />
    </div>
  </div>
</template>

<script>
import Item from './Item.vue'

export default {
  name: 'ItemList',
  components: {
    Item
  },
  props: {
    products: {
      type: Array,
      required: true
    }
  },
  methods: {
    handleAddToCart(product) {
      console.log(`Adding product to cart: ${product.name}`)
      console.log('Product Details:', product)
    }
  },
  computed: {
    total() {
      return this.items.filter((item) => item.selected).reduce((sum, item) => sum + item.price, 0)
    }
  }
}
</script>

<style scoped>
.product-list {
  max-width: 1200px;
  margin: 0 auto;
  padding: 20px;
  background-color: #f8f9fa;
  border-radius: 8px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}

.product-list h2 {
  font-size: 24px;
  color: #333;
  margin-bottom: 20px;
  text-align: center;
}

.products-container {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
  justify-content: center;
}

.products-container > * {
  flex: 1 1 300px;
  max-width: 300px;
}
</style>
