<template>
  <div className="card col-3">
        <img :src="product.image" :alt="product.title" className='img w-50' />
        <div className="card-body">
            <p className="card-text">{{ product.description }}</p>
        </div>
    </div>
</template>

<script>
export default {
  props: {
    product: {
      type: Object,
      required: true
    }
  }
};
</script>

<style scoped>
/* Add scoped styles here if needed */
</style>