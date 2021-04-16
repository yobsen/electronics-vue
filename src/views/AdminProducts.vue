<template lang="pug">
.admin-products
  .admin-products__button-container
    .admin-products__add-button(@click="showProductForm =! showProductForm" :class="{ 'is-clicked': showProductForm === true }") New Product
  ProductForm(v-show="showProductForm == true")
  .admin-products-catalog
    .admin-products-catalog__container
      .admin-products-catalog__item(v-for="product in products")
        .admin-products-catalog__delete-icon(@click="deleteProduct(product.id)")
          img(src="@/assets/img/trash-icon.svg")
        .admin-product-catalog__edit-icon
        ProductCard(
          :productImage=`require("@/assets/img/sample-image-5.jpg")`
          :product="product"
        )
</template>

<script>
import ProductCard from "@/components/products/ProductCard.vue"
import ProductForm from "@/components/products/ProductForm.vue"

export default {
  components: { ProductCard, ProductForm },
  data() {
    return {
      products: [],
      showProductForm: false
    }
  },
  async created() {
    this.getProducts()
  },
  methods: {
    async getProducts() {
      await this.$store.dispatch("product/getProducts")
      this.products = this.$store.getters["product/products"]
    },
    async deleteProduct(id) {
      await this.$store.dispatch("product/deleteProduct", id)
      this.getProducts()
    }
  }
}
</script>

<style lang="sass">
.admin-products
  &-catalog
    display: flex
    justify-content: center
    align-items: center
    min-height: 80vh

  &-catalog__container
    display: grid
    grid-gap: 3em
    grid-template-columns: 1fr 1fr 1fr 1fr

  &-catalog__item
    position: relative

  &-catalog__delete-icon
    position: absolute
    cursor: pointer

    img
      max-width: 25px
      max-height: 25px

  &__button-container
    position: sticky
    top: 4em
    z-index: 4
    display: flex
    justify-content: flex-end
    padding-right: 5em
    padding-top: 1em

  &__add-button
    border: 2px solid #5664b9
    background-color: white
    font-weight: 700
    border-radius: 50px
    padding: 0.75em 1em
    display: block
    text-align: center

  &__add-button:hover, .is-clicked
    color: white
    background-color: #5664b9
    cursor: pointer
</style>
