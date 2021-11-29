<template>
    <div class="cart-item-card">
        <h3>Cart Total: Php {{ cart_total.toFixed(2) }} </h3>
        <input v-model="coupon" placeholder="Enter coupon">
        <input v-model.number="money" type="number" placeholder="Enter payment amount">
        <button class="view-item" @click="checkCoupon()">Checkout</button>
    </div>
</template>

<script>
export default {
    computed: {
        cart_total(){
            return this.$store.getters.cartTotal()
        },
        checkCoupon(){
            return this.$store.getters.cartCoupon()
        }
    }
}
</script>