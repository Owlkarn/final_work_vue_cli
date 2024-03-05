<script>
export default {
  name: "ProductDetails",
  data() {
    return {
      products: [
        {
          name: "Ноутбук",
          price: 1000,
          available: true
        },
        {
          name: "Смартфон",
          price: 500,
          available: false
        },
        {
          name: "Планшет",
          price: 300,
          available: true
        }
      ],
    };
  },
  computed: {
    formattedPrice() {
      return function(product) {
        return '$' + product.price;
      };
    }
  },
}
</script>

<template>
<div v-for="(product, index) in products" :key="index">
  <h1 class="productName">{{ product.name }}</h1>
  <p class="productPrice">{{ formattedPrice(product) }}</p>
  <p v-if="product.available" class="productAvailable">Available</p>
  <p v-else class="productAvailable">Out of stock</p>
</div>
</template>

<style lang="scss" scoped>

</style>