<template lang="pug">
.product
  .product-image
    img(src="@/assets/img/sample-image-5.jpg")
  .product-info
    .product-info__title {{ product.name }}
    .product-info__price {{ product.price }}
    ul.product-info__description
      li {{ product.desc }}
    .product-info__add-to-cart-button(v-if="!isProductAdded" @click="addProduct") ADD TO CART
    .product-info__add-to-cart-button.product-info__add-to-cart-button--added(v-else @click="removeProduct") ADDED
</template>

<script>
export default {
  data() {
    return {
      isProductAdded: false,
      id: this.$route.params.id,
      product: {
        id: 1,
        name: "Super Svin",
        price: "$2.5",
        desc: "Umeet hrukat'"
      }
    }
  },
  methods: {
    addProduct() {
      this.isProductAdded = true
    },
    removeProduct() {
      this.isProductAdded = false
    }
  }

  // async created() {
  //   await this.$store.dispatch("product/getProduct", this.id)
  //   this.product = this.$store.getters["product/product"]
  // }
}
</script>

<style lang="sass">
.product
  min-height: 80vh
  display: flex
  justify-content: center
  align-items: center

  &-image
    height: 400px
    width: 400px
    padding-right: 100px
    display: flex
    justify-content: center
    align-items: center

    img
      width: 100%
      height: 100%

  &-info
    padding-left: 50px
    height: 400px
    width: 400px

  &-info__title
    font-size: 2.25rem
    font-weight: 700

  &-info__price
    font-size: 1.25rem
    font-weight: 700
    padding: 5px 0px

  &-info__description
    list-style: inside
    padding: 0px

    li::marker
      color: #5664b9

  &-info__add-to-cart-button
    border: 2px solid #5664b9
    font-weight: 700
    border-radius: 50px
    padding: 16px 20px
    display: block
    text-align: center
    cursor: pointer

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
