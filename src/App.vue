<script setup>





</script>

<template>
  <!-- Header -->
  <header>
    <h1>My E-commerce Store</h1>
    <nav>
      <ul>
        <li><a href="#">Home</a></li>
        <li><a href="#">Products</a></li>
        <li><a href="#">Cart</a></li>
        <li><a href="#">Contact</a></li>
      </ul>
    </nav>
  </header>

  <!-- Main Content -->
  <main>
    <section class="product">
      <img src="https://images.pexels.com/photos/90946/pexels-photo-90946.jpeg?cs=srgb&dl=pexels-math-90946.jpg&fm=jpg" alt="Product 1">
      <h2>Product 1</h2>
      <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit.</p>
      <button>Add to Cart</button>
    </section>

    <section class="product">
      <img src="https://cdn.shopify.com/s/files/1/2303/2711/files/2_e822dae0-14df-4cb8-b145-ea4dc0966b34.jpg?v=1617059123" alt="Product 2">
      <h2>Product 2</h2>
      <p>Nulla sit amet sem volutpat, congue lorem nec, hendrerit ex.</p>
      <button>Add to Cart</button>
    </section>

    <!-- Add more product sections as needed -->

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

button {
  background-color: #333;
  color: #fff;
  padding: 5px 10px;
  border: none;
  cursor: pointer;
}
</style>
