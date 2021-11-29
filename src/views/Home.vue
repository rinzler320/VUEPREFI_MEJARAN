<template>
  <div class="home">
    <ItemViewDrawer
    :product="product"
    :active="active.product_drawer"
    v-on:close-product-drawer="closeProductDrawer()" />
    
    <div class="item-cards">
      <ItemCards
      v-for="product in items" 
      :key="product.id"
      :product="product"
      v-on:item-view="viewItem($event)"/>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import items from '../data/items.js';
import ItemCards from '../components/items/ItemCards.vue';
import ItemViewDrawer from '../components/items/ItemViewDrawer.vue';

export default {
  name: "Home",
  components: {
    ItemCards, ItemViewDrawer
  },
  data(){
    return{
      items: items,
      product: null,
      active:{
        product_drawer: false
      }

    }
  },
  methods: {
    viewItem(product){
      this.product=product
      this.active.product_drawer = true
      console.log(this.product)
    },
    closeProductDrawer(){
      this.active.product_drawer = false
    }
  }
};
</script>

<style lang="scss">
  .item-cards{
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
  }
</style>
