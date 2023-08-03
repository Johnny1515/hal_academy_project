<script setup>
import FormProduct from './components/FormProduct.vue';
import { reactive } from 'vue';
import ParentB from './components/ParentB.vue';



const state = reactive({
  products:[]
})
function onCreateProduct(data){
  state.products.push(data);
}
</script>

<template>
  <!-- Header -->
  <header>
    <h1>Simeple Vue App</h1>
    <!-- <nav>
      <ul>
        <li><a href="#">Home</a></li>
        <li><a href="#">Products</a></li>
        <li><a href="#">Cart</a></li>
        <li><a href="#">Contact</a></li>
      </ul>
    </nav> -->
  </header>

  <!-- Main Content -->
  <main>
    
    <FormProduct @onSuccess="onCreateProduct" />
    <ParentB :products="state.products" />
  </main>

  <!-- Footer -->
  <footer>
    <p>&copy; 2023 My E-commerce Store. All rights reserved.</p>
  </footer>
</template>

<style scoped>
body {
  font-family: Arial, sans-serif;
  margin: 0;
  padding: 0;
}

header {
  background-color: #333;
  color: #fff;
  padding: 10px;
}

header h1 {
  margin: 0;
}

nav ul {
  list-style-type: none;
  padding: 0;
  margin: 0;
}

nav li {
  display: inline;
  margin-right: 20px;
}

nav a {
  text-decoration: none;
  color: #fff;
}

main {
  padding: 20px;
}



button {
  background-color: #333;
  color: #fff;
  padding: 5px 10px;
  border: none;
  cursor: pointer;
}
</style>
