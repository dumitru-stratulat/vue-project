<script >
export default {
name: "ProductList",
props: ["products"],
methods:{
    buy: function (product) {
        this.$emit("add-item-to-cart", product);
    },
}
}
</script>

<template>
  <div >
           <p>Subject:</p>
                <div v-for="(product,index) in products" v-bind:key="index">
                    <div class="cart">
                     
                        <p>Subject:{{product.topic}}</p>
                        <p>Price:{{product.price}}</p>
                        <p>Spaces:{{product.space}}</p>
                        <p>Location:{{product.location}}</p>
                        <button v-on:click="buy(product)" v-bind:disabled="product.space == 0">Add to cart</button>

                    </div>
                </div>
            </div>
  <!-- </div> -->
</template>