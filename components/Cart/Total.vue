<template>
  <div class="total-price container mt-5" v-if="totalPrice > 0">
    <button class="px-4 py-3">
      <img src="@/assets/wallet.png" alt="wallet" width="30" /> Payment Methods
    </button>

    <h3>{{ totalPrice.toFixed(2) }}$</h3>
  </div>
</template>

<script>
import { mapGetters } from 'vuex'
export default {
  computed: {
    ...mapGetters(['totalPrice']),
  },
}
</script>

<style lang="scss" scoped>
.total-price {
  @include between(row);
  flex-wrap: wrap;
  button {
    img {
      filter: invert(1);
    }
  }
}
@media (max-width: 550px) {
  button {
    padding: 15px 10px !important;
  }
}
@media (max-width: 320px) {
  button {
    padding: 10px 5px !important;
  }
}
</style>
