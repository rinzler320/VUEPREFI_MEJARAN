<template>
  <div>
        <h1>Your Cart</h1>

        <CartItemCard
            v-for="product in products" 
            :key="product.id"
            :product="product" />

        <CartSummaryCard
            :products="products" />
        
  </div>
</template>

<script>
import CartItemCard from '../components/cart/CartItemCard.vue';
import CartSummaryCard  from '../components/cart/CartSummaryCard.vue';

export default {
    components: {
        CartItemCard, CartSummaryCard
    },
    computed: {
        products(){
            return this.$store.getters.cartItems
        }
    }
};
</script>
