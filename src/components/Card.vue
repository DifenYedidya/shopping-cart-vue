<template>
  <div v-for="product in products" :key="product.id" class="card">
    <img
      src="https://statik.tempo.co/data/2022/03/09/id_1093577/1093577_720.jpg"
      class="card-img-top"
      alt="iphone"
    />
    <div class="card-header">Smartphones</div>
    <div class="card-body">
      <h5 class="card-title">{{ product.title }}</h5>
      <p class="card-text bold">{{ product.description }}</p>
      <p class="price">{{ product.price }}</p>
      <div class="flex-center">
        <p class="percentage">{{ product.discountPercentage }}</p>
        <p class="disc-price">Rp.6.600.000</p>
      </div>
      <div class="flex-center rating">
        <img src="../assets/img/star.png" class="star" />
        <div class="score">{{ product.rating }}</div>
      </div>
      <div class="flex-center btn">
        <img src="../assets/img/shopping-cart.png" class="cart" alt="cart" />
        <a href="#" class="btn-text">Add to Cart</a>
      </div>
    </div>
  </div>
</template>

<script>
// import Products from '../data/products.json'
// import Products from '../data/product.js'
//https://dummyjson.com/products
export default {
  name: "ProductList",
  data() {
    return {
      products: [],
    };
  },
  methods: {
    async getData() {
      try {
        let response = await fetch("https://dummyjson.com/products");
        this.products = await response.json();
      } catch (error) {
        console.log(error);
      }
    },
  },
  created() {
    this.getData();
  },
  // mounted() {
  //   axios
  //     .get("https://dummyjson.com/products")
  //     .then((response) => (this.products = response));
  // },
};
</script>
