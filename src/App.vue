<script setup>
import Card from "./components/Card.vue";
// import CheckoutCard from "./components/CheckoutCard.vue";
import "bootstrap/dist/css/bootstrap.min.css";
import "bootstrap";
</script>

<template>
  <div class="main">
    <div class="left-side">
      <Card class="products-list" />
    </div>
    <div class="right-side">
      <CheckoutCard />
    </div>
  </div>
</template>
