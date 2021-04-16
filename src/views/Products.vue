<template lang="pug">
.products
  .products__item(v-for="product in products")
    ProductCard(
      :productImage=`require("@/assets/img/sample-image-5.jpg")`
      :product="product"
    )
</template>

<script>
import ProductCard from "@/components/products/ProductCard.vue"

export default {
  components: { ProductCard },
  data() {
    return {
      products: [
        {
          id: 1,
          name: "Super Svin",
          centi_price: "$2.5",
          desc: "Umeet hrukat'"
        },
        { id: 2, name: "Super Svin 3000", centi_price: "$2.5", desc: "Umeet pukat'" }
      ]
    }
  }
  // async created() {
  //   await this.$store.dispatch("product/getProducts")
  //   this.products = this.$store.getters["product/products"]
  // }
}
</script>

<style lang="sass">
.products
  min-height: 50vh
  padding: 80px 80px 0px 80px
  display: grid
  grid-gap: 80px
  grid-template-columns: 1fr 1fr 1fr 1fr
</style>
