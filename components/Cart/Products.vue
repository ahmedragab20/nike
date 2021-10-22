<template>
  <div class="cart-products container">
    <div class="product-container text-center">
      <div class="row">
        <div class="col-md-4">
          <figure class="image-container">
            <div class="image">
              <img :src="item.img" :alt="item.name" />
            </div>
          </figure>
        </div>
        <div class="col-md-4">
          <figure>
            <h3>{{ item.quantity }} {{ word }}</h3>
            <div class="btns">
              <button @click="addToCart()">+</button>
              <button @click="removeFromCart()">-</button>
            </div>
          </figure>
        </div>
        <div class="col-md-4">
          <figure>
            <h3>Total Price</h3>
            <p>{{ totalProductPrice.toFixed(2) }}$</p>
          </figure>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['item'],
  computed: {
    word() {
      return this.item.quantity == 1 ? 'Piece' : 'Pieces'
    },
    totalProductPrice() {
      return this.item.price * this.item.quantity
    },
  },
  methods: {
    addToCart() {
      this.$store.commit('addToCart', this.item)
    },
    removeFromCart() {
      this.$store.commit('removeFromCart', this.item)
    },
  },
}
</script>

<style lang="scss" scoped>
.product-container {
  figure {
    @include center(column);
    position: relative;
    height: $full;

    .btns {
      button {
        transition: 0.2s;
        margin: 0 1px;
        &:hover {
          transform: scale(0.9);
        }
      }
    }
  }
  .image-container {
    img {
      width: 95%;
      height: 95%;
      object-fit: contain;
    }
  }
}
</style>
