<script setup>
import Button from './Button.vue';

const props = defineProps({
    carts:{
        type:Array,
        required:false,
        default:[]
    },
    qty:{
        type:Array,
        required:false,
        default:[]
    }
})

</script>
<template>
    <div class="cart-container">
    <h2>Shopping Cart</h2>
    <ul class="cart-list">
      <li class="cart-item" v-for="(cart ,index) in props.carts">
        <div class="item-details">
            <img src="https://images.pexels.com/photos/90946/pexels-photo-90946.jpeg?cs=srgb&dl=pexels-math-90946.jpg&fm=jpg" alt="Product 1">
          <div class="item-info">
            <h3>{{ cart.title }}</h3>
            <p>Quantity: {{ props.qty[index] }}</p>
            <Button class="danger-button">Remove</Button>
          </div>
        </div>
      </li>
    </ul>
  </div>

</template>


<style scoped>
 .cart-container {
  max-width: 600px;
  margin: 0 auto;
  padding: 20px;
}

h2 {
  text-align: center;
}
.item-details{
    width:100%;
    display: flex;
    justify-content: space-between !important;
}
.item-details > img {
    object-fit: cover;
    object-position: center;
    width:100%;
    height:100%;
}
.cart-list {
  list-style: none;
  padding: 0;
}

.cart-item {
  display: flex;
  align-items: center;
  border: 1px solid #ccc;
  border-radius: 4px;
  padding: 10px;
  margin-bottom: 10px;
}

.cart-item img {
  max-width: 80px;
  margin-right: 10px;
}

.item-info {
  display: flex; 
  gap:5px;
  align-items: center;
}

</style>