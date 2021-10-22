<template>
  <div>
    <Nav />
    <Nuxt />
    <Footer />
  </div>
</template>

<script>
export default {
  mounted() {
    return setInterval(this.$store.commit('updateCartStorage'))
  },
}
</script>

<style lang="scss" scoped></style>
