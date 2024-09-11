<template>
  <div class="product-item">
    <img :src="product.image" :alt="product.name" class="product-image" />
    <h3>{{ product.name }}</h3>
    <p class="product-price">Price: ₱{{ product.price }}</p>
    <button @click="addToCart" :aria-label="`Add ${product.name} to cart`">Add to Cart</button>
  </div>
</template>

<script>
export default {
  name: 'Item',
  props: {
    product: {
      type: Object,
      required: true
    }
  },
  methods: {
    addToCart() {
      this.$emit('add-to-cart', this.product)
    }
  }
}
</script>

<style scoped>
.product-item {
  background-color: antiquewhite;
  border-radius: 8px;
  padding: 15px;
  text-align: center;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  transition: transform 0.2s ease-in-out;
  max-width: 200px;
}

.product-item:hover {
  transform: translateY(-5px);
}

.product-item h3 {
  font-size: 16px;
  color: #333;
  margin-bottom: 15px;
}

.product-price {
  font-size: 16px;
  color: #556;
  margin: 15px 0;
}

.product-item button {
  background-color: red;
  color: white;
  border: none;
  padding: 10px 15px;
  border-radius: 4px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

.product-item button:hover {
  background-color: darkred;
}
</style>
