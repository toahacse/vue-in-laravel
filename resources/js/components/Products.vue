<template>
  <div>
    <h1>Products List</h1>
    <div className='row m-0 p-0'>
        <Product v-for="product in products" :key="product.id" :product="product" />
    </div>
  </div>
</template>

<script>
import Product from './Product.vue';

export default {
  components: {
    Product
  },
  data() {
    return {
      products: []
    };
  },
  async mounted() {
    try {
      const response = await fetch("https://fakestoreapi.com/products");
      if (!response.ok) {
        throw new Error('Failed to fetch products');
      }
      this.products = await response.json();
    } catch (error) {
      console.error('Error fetching products:', error);
    }
  }
};
</script>

<style scoped>
/* Add scoped styles here if needed */
</style>