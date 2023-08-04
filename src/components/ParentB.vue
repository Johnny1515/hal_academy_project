<script setup>
import CardProduct from './CardProduct.vue';
import { reactive } from 'vue';
import CartListProduct from './CartListProduct.vue';
const props = defineProps({
    products:{
        type:Array, 
        required:false,
        default:[]
    }
})
const state = reactive({
    carts:[],
    qty:[]
})
function onAddToCart(id_product){
    const find_product_index = props.products.findIndex(product => product.id === id_product)
    if(find_product_index !== -1){
        const product = props.products[find_product_index]
        const find_cart_index = state.carts.findIndex(cart  => cart.id === id_product)
        if(find_cart_index !== -1 ){
            state.qty[find_cart_index]++;
        }else{
            state.carts.push(product)
            state.qty.push(1)
        }
    }
}

</script>
<template>
    <div>
        <h2 style="text-align: center; color:green">Parent B Content</h2>
        <div style="display: flex;">
            
            <div class="grid">
                <CardProduct v-for="(product ,index) in props.products" 
                :key="index"
                :title="product.title"
                :id="product.id"
                @addToCart="onAddToCart"
                />
            </div>
            <CartListProduct :carts="state.carts" :qty="state.qty" />
    
        </div>

    </div>

</template>


<style scoped>
.grid {
    display: grid;
    gap:5px;
    grid-template-columns: 1fr 1fr 1fr 1fr 1fr;
}
</style>