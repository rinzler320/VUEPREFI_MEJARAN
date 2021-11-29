<template>
    <div class="cart-item-card">
        <div class="header">
            <h3> {{ product.name }} </h3>
            <img class="image" v-bind:src="product.img">
            <h5 class="price">Price: Php {{ product.price.toFixed(2) }}</h5>
            <h4>In Cart: {{ product.quantity }} </h4>.
            <h4>Total Cost: {{ item_cost.toFixed(2) }} </h4>
        </div>
        <div class="button-container">
                <input type="number" class="quantity">
                <br>
                <button class="remove" @click="removefromCart()">Remove</button>
                <button class="add" @click="addtoCart()">Add</button>
            </div>
        <p> {{ description }} </p>
    </div>
</template>

<script>
export default {
    props: ['product'],
    computed: {
        description(){
            return this.product.description.substring(0, 100)
        },
        item_cost(){
            return this.product.price * this.product.quantity
        }
    }

}
</script>

<style lang="scss">
.cart-item-card{
    width: 90%;
    margin: 5%;
    background-color: white;
    box-shadow: 0 0 5px gray;
    border-radius: 5px;
    padding: 10px;
    text-align: left;

    .header{
        display: flex;
        justify-content: space-around;

        img.image{
            width: 15vw;
            height: 15vh;
            
        }

        h5.price{
            color: gray;
        }
    }
    .button-container{
        button {
            width: 150px;
            border: none;
            padding: 10px;
            border-radius: 5px;
            margin: 0 5px 50px 5px;
            cursor: pointer;
        }

    }
}
</style>