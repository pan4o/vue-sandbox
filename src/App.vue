<template>
  <div>
    <h1>{{ message }}</h1>
    <test-input :msg="message" @messageChanged="message = $event"></test-input>
    <product-list @viewDetails="viewDetails"></product-list>
    <p v-if="product_title">Вы нажали компонент под номером: {{product_title}}</p>
  </div>
</template>

<script>
  import TestInput from './components/TestInput.vue';
  import ProductList from './components/ProductsList.vue';

  export default {
    data () {
      return {
        message: 'This is a great Message!',
        product_title: ''
      }
    },
    methods: {
      viewDetails(id) {
        this.product_title = id;
      }
    },
    components: {
      'test-input': TestInput,
      'product-list': ProductList
    }
  }
</script>
