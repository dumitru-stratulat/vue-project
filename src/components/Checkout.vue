<script >
export default {
name: "Checkout",
props: ["cart"],
methods:{
    removeFromCart: function (product) {
        this.$emit("remove-item-from-cart", product);
    },
}
}
</script>

<template>
<div>
    <h1>Cart:</h1>
            <div class="cardContainer">
                <div v-for="(product,index) in cart" :key="index">
                    <div class="cart" v-if='product.space > 0'>
                        <p>Subject:{{product.topic}}</p>
                        <p>Price:{{product.price}}</p>
                        <p>Spaces:{{product.space}}</p>
                        <p>Location:{{product.location}}</p>
                        <button v-on:click="removeFromCart(product)" v-bind:disabled="product.space == 0">Remove from
                            cart
                        </button> 
                    </div>
                </div>
            </div>
</div>
</template>