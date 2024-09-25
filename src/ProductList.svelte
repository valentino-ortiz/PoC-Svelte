<!-- src/ProductList.svelte -->
<script>
  import { products } from './data/products.js';

  let selectedCategory = 'All';
  let showAvailableOnly = false;
  let filteredProducts = products;

  const categories = ['All', ...new Set(products.map((p) => p.category))];

  const filterProducts = () => {
    filteredProducts = products.filter((product) => {
      const matchesCategory =
        selectedCategory === 'All' || product.category === selectedCategory;
      const matchesAvailability = !showAvailableOnly || product.available;
      return matchesCategory && matchesAvailability;
    });
  };

  const handleFilterClick = () => {
    filterProducts();
  };
</script>

<div class="filters">
  <label for="category">Categoría:</label>
  <select id="category" bind:value={selectedCategory}>
    {#each categories as category}
      <option value={category}>{category}</option>
    {/each}
  </select>

  <label>
    <input type="checkbox" bind:checked={showAvailableOnly} />
    Mostrar solo disponibles
  </label>

  <button class="button" on:click={handleFilterClick}> Filtrar </button>
</div>

<div class="product-list">
  {#each filteredProducts as product}
    <div class="product-card">
      <img src={product.image} alt={product.name} />
      <h3>{product.name}</h3>
      <p class="price">${product.price.toFixed(2)}</p>
      {#if product.available}
        <p style="color: green;">Disponible</p>
      {:else}
        <p style="color: red;">No disponible</p>
      {/if}
    </div>
  {/each}
</div>
