<template>
  <div>
    <ProductsSkeleton :products="products" />
    <h2>{{totalProducts}}</h2>
    <fieldset v-if="products.length !== 0">
      <legend>Filter By</legend>
      <label>
        All
        <input type="radio" name="gender" value="all" checked v-on:change="filterProducts" />
      </label>
      <label>
        Men
        <input type="radio" name="gender" value="men" v-on:change="filterProducts" />
      </label>
      <label>
        Women
        <input type="radio" name="gender" value="women" v-on:change="filterProducts" />
      </label>
    </fieldset>
    <ol>
      <li v-for="product in products" v-bind:key="product.id">
        <h3>
          <span class="sr-only">product name:</span>
          {{product.name.en}}
        </h3>
        <figure>
          <img
            :src="product.masterVariant.images[0].url"
            :alt="product.name.en"
            loading="lazy"
            width="100"
            height="100"
          />
        </figure>
      </li>
    </ol>
  </div>
</template>

<script>
import ProductsSkeleton from "./ProductsSkeleton.vue";

export default {
  name: "Products",
  components: {
    ProductsSkeleton
  },
  data: function() {
    return {
      totalProducts: "",
      productsURL:
        "https://api.commercetools.co/frontend-interview-exercise/product-projections",
      products: [],
      originalProducts: []
    };
  },
  methods: {
    fetchProducts() {
      fetch(this.productsURL, {
        headers: {
          Authorization: `Bearer ${this.$attrs.APIKey}`
        }
      })
        .then(response => {
          return response.json();
        })
        .then(myJson => {
          this.totalProducts = `Showing ${myJson.count} of ${myJson.total} Products`;
          this.products = myJson.results;
          this.originalProducts = this.products;
        });
    },
    filterProducts(event) {
      const value = event.target.value;
      // FIXME: There must be a better way to do this without all this reassigning
      this.products = this.originalProducts;
      if (value !== "all") {
        this.products = this.products.filter(product => {
          return product.masterVariant.attributes.some(item => {
            if (item.value.key !== undefined) {
              return item.value.key === value;
            }
          });
        });
      }
    }
  },
  created() {
    this.fetchProducts();
  }
};
</script>

<style scoped>
h2 {
  margin-top: 1em;
  padding-left: 0.75em;
  font-family: "Oswald", sans-serif;
}

fieldset {
  border: none;
  margin-top: 1em;
  padding-left: 1.25em;
}

legend {
  color: #4b4b4b;
  font-weight: bold;
  font-family: "Oswald", sans-serif;
}

label {
  font-size: 1.25em;
  margin-right: 1em;
}

ol {
  display: flex;
  flex-wrap: wrap;
  list-style-type: none;
  margin-top: 1.5em;
}

li {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  flex: 0 0 calc(25% - 2.5em);
  margin: 1.25em;
  padding: 0.5em;
  background: #fff;
  text-align: center;
  border-radius: 0 0 0.5em 0.5em;
  box-shadow: 0 1px 1px rgba(0, 0, 0, 0.12), 0 2px 2px rgba(0, 0, 0, 0.12),
    0 4px 4px rgba(0, 0, 0, 0.12), 0 8px 8px rgba(0, 0, 0, 0.12),
    0 16px 16px rgba(0, 0, 0, 0.12);
}

h3 {
  font-size: 1em;
}

figure {
  display: inline-flex;
  margin-top: 1em;
}

img {
  object-fit: contain;
  height: 200px;
}

@media only screen and (max-width: 1024px) {
  li {
    flex-basis: calc(33.333% - 2.5em);
  }
}

@media only screen and (max-width: 768px) {
  li {
    flex-basis: calc(50% - 2.5em);
  }
}

@media only screen and (max-width: 480px) {
  li {
    flex: 100%;
  }
}
</style>
