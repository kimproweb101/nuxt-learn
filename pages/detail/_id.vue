<template>
  <div>
    {{ product }}
    <img :src="product.imageUrl" :alt="product.name" />
    <p>name: {{ product.name }}</p>
    <p>pricce: {{ product.price }}</p>
  </div>
</template>

<script>
import { fetchProductById } from '@/api/index'
export default {
  async asyncData({ params }) {
    const response = await fetchProductById(params.id)
    const product = response.data
    return { product }
  },
}
</script>

<style scoped>
.container {
  display: flex;
  justify-content: center;
  margin: 2rem 0;
}
.product-image {
  width: 500px;
  height: 375px;
}
.side-panel {
  display: flex;
  flex-direction: column;
  justify-content: center;
  width: 220px;
  text-align: center;
  padding: 0 1rem;
}
</style>
