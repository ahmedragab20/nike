<template>
  <div>
    <HomeLGHeader />
    <HomeSMHeader />
    <Gym />
    <div class="container mt-5">
      <h2 class="text-center my-4">Products</h2>
      <div class="row">
        <div
          class="col-lg-3 col-md-6"
          v-for="product in products"
          :key="product.id"
        >
          <Products :product="product" />
        </div>
      </div>
    </div>
    <Article />
  </div>
</template>

<script>
import products from '@/data/db'
export default {
  data() {
    return {
      products,
    }
  },
  head: {
    title: 'Home',
  },
}
</script>
<style lang="scss" scoped></style>
