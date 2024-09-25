<!-- src/App.svelte -->
<script>
  import ProductList from './ProductList.svelte';
</script>

<header class="header">
  <div class="logo">
    <img src="/assets/G.png" alt="La Gallega" />
    <span>La Gallega</span>
  </div>
  <div class="icons">
    <span class="icon search-icon">&#128269;</span>
    <span class="icon user-icon">&#128100;</span>
  </div>
</header>

<nav class="navbar">
  <button class="category-button">Categ1</button>
  <button class="category-button">Categ2</button>
  <button class="category-button">Categ3</button>
  <button class="category-button">Categ4</button>
  <button class="category-button">Categ5</button>
  <button class="category-button">Categ6</button>
  <button class="category-button">Categ7</button>
  <button class="category-button">Categ8</button>
  <button class="category-button">Categ9</button>
</nav>

<main class="main-content">
  <h2>Productos</h2>
  <ProductList />
</main>

<footer>&copy; 2024 La Gallega. Todos los derechos reservados.</footer>
