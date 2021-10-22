<template>
  <nav>
    <div class="container">
      <div class="logo">
        <nuxt-link to="/">
          <img src="@/assets/nike.png" width="40" />
        </nuxt-link>
      </div>
      <div class="links" :class="{ active: isActive }">
        <ul>
          <li>
            <nuxt-link to="/" exact>Home</nuxt-link>
          </li>
          <li>
            <nuxt-link to="/Cart">Cart</nuxt-link>
          </li>
          <li>
            <a href="#">Help?</a>
          </li>
        </ul>
      </div>
      <div
        class="burger"
        @click="isActive = !isActive"
        :class="{ active: isActive }"
      >
        <div class="line-1"></div>
        <div class="line-2"></div>
        <div class="line-3"></div>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  data() {
    return {
      isActive: false,
    }
  },
}
</script>

<style lang="scss" scoped>
nav {
  width: 100%;
  min-height: 10vh;
  position: fixed;
  top: 0;
  left: 0;
  z-index: 9;
  -webkit-backdrop-filter: $blur;
  -moz-backdrop-filter: $blur;
  -ms-backdrop-filter: $blur;
  -o-backdrop-filter: $blur;
  backdrop-filter: $blur;

  .container {
    @include between(row);
    min-height: 10vh;

    .links {
      width: 50%;
      min-height: 10vh;
      display: flex;
      justify-content: flex-end;
      align-items: center;

      ul {
        width: 50%;
        display: flex;
        justify-content: space-around;
        align-items: center;
        z-index: 999;

        a {
          padding: 7px 14px;
        }

        .nuxt-link-active {
          border: 1px solid #d1d1d1;
          border-radius: 5px;
        }
      }
    }

    .burger {
      padding: 5px;
      border-radius: 5px;
      display: none;
      cursor: pointer;
      z-index: 3;

      * {
        transition: all 0.3s ease-in-out;
      }

      div {
        width: 25px;
        height: 1px;
        margin: 5px;
        background-color: $dark;
      }
    }
  }
}

@media (max-width: 768px) {
  nav {
    * {
      color: rgba(255, 255, 255, 0.781);
    }
    .container {
      .logo {
        img {
          width: 35px;
        }
      }

      .links {
        position: absolute;
        top: 0vh;
        right: -50vw;
        height: 100vh;
        width: 50vw;
        background-color: $dark;
        transition: all 0.3s ease-in-out;
        display: flex;
        justify-content: center;
        align-items: center;

        &.active {
          right: 0;
        }

        ul {
          width: 100%;
          height: 60%;
          flex-direction: column;
        }
      }

      .burger {
        display: inline-block;

        &.active {
          * {
            background-color: #fff;
          }
          .line-1 {
            transform: rotate(45deg) translate(5px, 4px);
          }
          .line-2 {
            opacity: 0;
          }
          .line-3 {
            transform: rotate(-45deg) translateY(-3px) translateX(5px);
          }
        }
      }
    }
  }
}
@media (max-width: 555px) {
  nav {
    .container {
      .links {
        right: -85vw;
        width: 85vw;
      }
    }
  }
}
</style>
