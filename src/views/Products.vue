<template lang="pug">
.products
  .products__item(v-for="product in products")
    ProductCard(
      :productImage=`require("@/assets/img/sample-image-5.jpg")`
      :product="product"
      @addProduct="addProduct"
      @removeProduct="removeProduct"
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
          name: "3D-printed box",
          price: "$2.5",
          desc: "Umeet hrukat'"
        },
        { id: 2, name: "3D-printed box black", price: "$35.5", desc: "Umeet pukat'" }
      ],
      addedProducts: []
    }
  },
  methods: {
    addProduct(product) {
      this.addedProducts.push(product)
    },
    removeProduct(product) {
      this.addedProducts = this.addedProducts.filter(addedProduct => addedProduct.id === product.id)
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
