<script setup>
import Button from './Button.vue';


const props = defineProps({
    title:{
        type:String, // String  | Boolean | Array | Number | Object
        required:false , // true | false 
        default: "" // this make default value before props is required = false make save error
    },
    id:{
        type:Number, // String  | Boolean | Array | Number | Object
        required:true , // true | false 
    }
})
const emits = defineEmits(["addToCart"])
function onAddByCard(){
    const id =  props.id
    emits("addToCart",id)
}
</script>
<template>
    <section class="product">
        <img src="https://images.pexels.com/photos/90946/pexels-photo-90946.jpeg?cs=srgb&dl=pexels-math-90946.jpg&fm=jpg" alt="Product 1">
        <h2>{{ props.title }}</h2>
        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit.</p>
        <Button @click="onAddByCard" >Add to Cart</Button>
    </section>

</template>


<style scoped>
 .product {
  max-width: 300px;
  margin: 0 auto;
  border: 1px solid #ccc;
  padding: 10px;
}

.product img {
  max-width: 100%;
  height: auto;
}

.product h2 {
  margin: 10px 0;
}
</style>