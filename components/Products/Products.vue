<template>
  <div class="products">
    <div class="product-card text-center position-relative">
      <div class="upper h-100">
        <img class="img-fluid" :src="product.img" :alt="product.name" />
        <h3 class="position-absolute text-capitalize">
          {{ product.name }}
        </h3>
      </div>
      <div class="context px-2">
        <p>{{ product.details }}</p>
        <figure class="d-flex justify-content-between align-items-center">
          <button @click="addToCart()">Buy Now!</button>
          <span>{{ product.price.toFixed(2) }}$</span>
        </figure>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['product'],
  methods: {
    addToCart() {
      this.$store.commit('addToCart', this.product)
    },
  },
}
</script>

<style lang="scss" scoped>
.products {
  .product-card {
    height: 270px;
    border-radius: 15px;
    box-shadow: 0px 0px 3px rgba(17, 17, 17, 0.3),
      0px -2px 3px rgba(17, 17, 17, 0.3);

    * {
      transition: $transition;
    }
    &:hover {
      .upper {
        transform: translateY(-120px);

        img {
          transform: rotate(20deg);
        }
      }

      .context {
        opacity: 1;
        pointer-events: all;
      }
    }

    .upper {
      position: relative;
      h3 {
        position: absolute;
        bottom: 30px;
        width: $full;
        text-align: center;
      }
    }

    .context {
      position: absolute;
      bottom: 0;
      left: 0;
      opacity: 0;
      pointer-events: none;
    }
  }
}
@media (max-width: 1024px) {
  .products {
    .product-card {
      .context {
        p {
          font-size: $sm;
        }
      }
    }
  }
}

@media (max-width: 985px) {
  .products {
    margin: 10px auto;
    .product-card {
      min-height: 295px;

      .upper {
        h3 {
          bottom: 20px;
        }
      }
    }
  }
}
@media (max-width: 590px) {
  .products {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;

    .product-card {
      min-height: 295px;
      width: 320px;

      .upper {
        h3 {
          bottom: 23px;
        }
      }
    }
  }
}
@media (max-width: 320px) {
  .products {
    margin: 5px;
    .product-card {
      min-height: 255px;
      width: 250px;
    }
  }
}
</style>
