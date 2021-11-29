<template>
    <div class="card">
        <h3>{{ product.name }}</h3>
        <img class="image" v-bind:src="product.img">
        <h5 class="price">Price: Php {{ product.price.toFixed(2) }}</h5>
        
        
        <button class="view-item" @click="$emit('item-view', product)">View Item</button>
    </div>
</template>

<script> 
export default {
    props:[
        ['product'],
        // computed/*:*/, {
        //     category() {
        //         return this.product.category.substring(0, 150)
        //     }
        // }
    ]
}
</script>

<style lang="scss">
    .card{
        width: 80%;
        margin: 10%;
        padding: 10px;
        border-radius: 5px;
        background-color: white;
        box-shadow: 0 0 5px gray;

        img.image{
            width: 15vw;
            height: 15vh;
            
        }

        h5.price{
            color: gray;
        }

        p.category{
            font-size: 1rem;
        }

        p.quantity{
            color: #42b983;
        }
    }
    button.view-item{
            padding: 10px;
            background-color: teal;
            border: none;
            color: white;
            font-weight: bold;
            font-size: 1rem;
            border-radius: 5px;
            cursor: pointer;
    }

    @media(min-width: 50px){
        .card{
            width: 350px;
            margin: 10px;
        }
    }
</style>