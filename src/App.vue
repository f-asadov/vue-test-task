<template>
  <div class="main">
    <Header v-bind:products="filteredProducts" />
    <Search v-on:inputChange="handleChange" />
    <ProductsTable v-bind:products="filteredProducts" v-on:deleteProduct="deleteProduct" />
  </div>
</template>

<script>
import axios from 'axios'
import Header from './components/Header.vue'
import Search from './components/Search.vue'
import ProductsTable from './components/Products-table.vue'


export default ({
  components: {
    Header, Search, ProductsTable
  },
  data() {
    return {
      products: [],
      searchQuery: '',
      index:'aa'
    }
  },
  methods: {
    async getProducts() {
      const t = await axios.get('https://dummyjson.com/products')
      this.products = t.data.products
    },
    handleChange(event) {
      const { value } = event.target
      this.searchQuery = value
    },
    deleteProduct(index) {
        this.products.splice(index, 1);
    }

  },
  mounted() {
    this.getProducts()
  },
  computed: {
    filteredProducts() {
      return this.products.filter(product => {
        return product.title.toLowerCase().includes(this.searchQuery.toLowerCase())
      })
    }
  }
})

</script>

<style>
*,
body {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Nunito Sans', sans-serif;
}

body {
  display: flex;
  height: 100vh;
  justify-content: center;
  align-items: center;
}

.main {
  box-shadow: rgba(0, 0, 0, 0.35) 0px 5px 20px;
  height: 60vh;

}
</style>