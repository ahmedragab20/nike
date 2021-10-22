<template>
  <div class="cart position-relative">
    <div class="clear" @click="clear" v-if="totalPrice > 0">
      <img src="@/assets/delete.png" alt="trash image" width="30" />
    </div>
    <div v-for="item in cartProducts" :key="item.id">
      <CartProducts :item="item" v-if="item.quantity > 0" />
    </div>
    <CartTotal />
    <h3 class="text-center" v-if="totalPrice <= 0">I'm Empty</h3>
  </div>
</template>

<script>
import { mapGetters } from 'vuex'
export default {
  computed: {
    ...mapGetters(['cartProducts', 'totalPrice']),
  },
  methods: {
    clear() {
      this.$store.commit('clearAll')
    },
  },
}
</script>

<style lang="scss" scoped>
.cart {
  margin-top: 12vh;

  .clear {
    width: 30px;
    height: 30px;
    position: absolute;
    top: 3vh;
    right: 10vw;
    z-index: 99;

    &:hover::after {
      transform: scale(1) translateY(0);
    }

    &::after {
      content: 'clear the cart';
      position: absolute;
      top: -30px;
      left: -40px;
      width: 100px;
      font-size: $sm;
      padding: 5px;
      background-color: rgb(223, 153, 166);
      border-radius: 8px;
      pointer-events: none;
      transform: scale(0) translateY(15px);
      color: #fff;
      opacity: 0.9;
      transition: $transition;
    }

    img {
      width: $full - 20;
      height: $full - 20;
      object-fit: contain;
      cursor: pointer;
      animation: trash 0.5s infinite;
    }
    @keyframes trash {
      0% {
        transform: rotate(0deg);
      }
      25% {
        transform: rotate(15deg);
      }
      50% {
        transform: rotate(0deg);
      }
      75% {
        transform: rotate(-15deg);
      }
      100% {
        transform: rotate(0deg);
      }
    }
  }
}
</style>
