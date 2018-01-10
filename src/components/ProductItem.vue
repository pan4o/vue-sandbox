<template>
  <div class="product-item">
    <h2><span class="index">{{product.index}}</span> {{product.title}}</h2>
    <span class="view-details" @click="viewDetails">View Details</span>
  </div>
</template>
<script>
  export default {
    props: ['product'],
    methods: {
      viewDetails() {
        this.$emit('viewDetails', this.product.id)
      }
    }
  }
</script>
<style scoped lang="scss">
  .product-item {
    border: 1px solid #000;
    margin-bottom: 10px;
    padding: 10px;

    .index {
      color: red;
    }

    .view-details {
      cursor: pointer;
      color: blue;
    }
  }
</style>
