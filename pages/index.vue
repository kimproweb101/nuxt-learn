<template>
  <div class="app">
    <main>
      <div>
        <!-- <SearchInput
          :search-keyword="searchKeyword"
          @input="updateSearchKeyword"
        ></SearchInput> -->
        <SearchInput
          v-model="searchKeyword"
          @search="searchProduct"
        ></SearchInput>
      </div>
      <ul class="">
        <li
          v-for="product in products"
          :key="product.id"
          class="item flex"
          @click="moveToDetailPage(product.id)"
        >
          <img
            class="product-image"
            :src="product.imageUrl"
            :alt="product.name"
          />
          <p>{{ product.name }}</p>
          <span>{{ product.price }}</span>
        </li>
      </ul>
    </main>
  </div>
</template>
<script>
import axios from 'axios'
import { fetchProductByKeyword } from '~/api'
import SearchInput from '~/components/SearchInput.vue'

export default {
  name: 'Index',
  components: { SearchInput },
  setup() {},
  async asyncData() {
    const response = await axios.get('http://localhost:3000/products')
    const products = response.data.map((item) => ({
      ...item,
      imageUrl: `${item.imageUrl}?random=${Math.random}`,
    }))
    return { products }
  },
  data() {
    return {
      searchKeyword: '',
    }
  },
  methods: {
    moveToDetailPage(id) {
      this.$router.push(`detail/${id}`)
    },
    async searchProduct() {
      const response = await fetchProductByKeyword(this.searchKeyword)
      this.products = response.data
    },
  },
}
</script>
<style scoped>
.flex {
  display: flex;
  justify-content: center;
}
.item {
  display: inline-block;
  width: 400px;
  height: 300px;
  text-align: center;
  margin: 0 0.5rem;
  cursor: pointer;
}
.product-image {
  width: 400px;
  height: 250px;
}
.app {
  position: relative;
}
.cart-wrapper {
  position: sticky;
  float: right;
  bottom: 50px;
  right: 50px;
}
.cart-wrapper .btn {
  display: inline-block;
  height: 40px;
  font-size: 1rem;
  font-weight: 500;
}
</style>
