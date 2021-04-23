<template lang="pug">
.product-item
  router-link(
    :to="{ name: 'Product', params: { id: product.id }}"
    class="product-item__card"
  )
    .product-item__image
      img(:src="productImage")
    .product-item__title {{ product.name }}
    .product-item__price {{ product.price }}
  .product-item__add-to-cart-button(v-if="!isProductAdded" @click="addProduct") ADD TO CART
  .product-item__add-to-cart-button.product-item__add-to-cart-button--added(v-else @click="removeProduct") ADDED
</template>

<script>
export default {
  props: {
    productImage: { type: String, default: "" },
    product: { type: Object, default: () => {} }
  },
  emits: {
    addProduct: null,
    removeProduct: null
  },
  data() {
    return {
      isProductAdded: false
    }
  },
  methods: {
    addProduct() {
      this.$emit("addProduct", this.product)
      this.isProductAdded = true
    },
    removeProduct() {
      this.$emit("removeProduct", this.product)
      this.isProductAdded = false
    }
  }
}
</script>

<style lang="sass">
.product-item
  padding-bottom: 80px

  &__card
    display: block
    max-width: 350px

  &__image
    max-height: 300px
    display: flex
    justify-content: center
    align-items: center

    img
      width: 100%
      height: 100%

  &__title
    text-align: center
    overflow: hidden
    white-space: nowrap
    text-overflow: ellipsis
    padding-top: 30px

  &__price
    font-size: 1.25rem
    font-weight: 600
    text-align: center
    padding: 10px 0px 20px

  &__add-to-cart-button
    border: 2px solid #5664b9
    font-weight: 700
    border-radius: 50px
    padding: 1em 1.25em
    display: block
    text-align: center

    &:hover
      color: white
      background-color: #5664b9
      cursor: pointer

    &--added
      background-color: #5664b9
      color: white

      &:hover
        color: white
        background-color: #5664b9
        cursor: pointer
</style>
