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

<style lang="scss" scoped></style>
