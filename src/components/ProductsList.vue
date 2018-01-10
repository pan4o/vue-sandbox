<template>
  <ul>
    <li v-for="product in products">
      <product-item :product="product" @viewDetails="viewDetails"></product-item>
    </li>
  </ul>
</template>
<script>
  import ProductItem from './ProductItem';

  export default {
    data() {
      return {
        products: [
          {
            id: 1,
            index: 1,
            title: 'google'
          },
          {
            id: 2,
            index: 2,
            title: 'amazon'
          },
          {
            id: 3,
            index: 3,
            title: 'microsoft'
          },
          {
            id: 4,
            index: 4,
            title: 'facebook'
          }
        ]
      }
    },
    methods: {
      viewDetails(id) {
        this.$emit('viewDetails', id);
      }
    },
    components: {
      'product-item': ProductItem
    }
  }
</script>
<style scoped lang="scss">
  li {
    list-style-type: none;
  }
</style>
