<template lang="pug">
.cart
  .cart-product(v-for="product in products")
    .cart-product__thumbnail
      img(src="@/assets/img/sample-image-4.jpg")
    router-link.cart-product__name(:to="{ name: 'Product', params: { id: product.id }}") {{ product.name }}  
    .cart-product__price {{ product.price }}
    img.cart-product__delete-icon(@click="removeProduct(product)" src="@/assets/img/trash-icon.svg")
</template>

<script>
export default {
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
      ]
    }
  },
  methods: {
    removeProduct(removingProduct) {
      this.products = this.products.filter(product => product.id === removingProduct.id)
    }
  }
}
</script>

<style lang="sass">
.cart
  min-height: 80vh
  display: flex
  flex-direction: column
  justify-content: center
  align-items: center

  .cart-product
    padding: 20px 0
    width: 1000px
    display: grid
    grid-template-areas: "thumbnail name price delete"
    grid-template-columns: 25% 40% 20% 15%

    &:not(:last-child)
      border-bottom: 1px solid #e5e5e5

    &__thumbnail
      max-height: 200px
      max-width: 200px
      display: flex
      justify-content: center
      align-items: center
      grid-area: thumbnail

      img
        width: 100%
        height: 100%

    &__name
      margin-left: 50px
      font-size: 1.5em
      font-weight: bold
      grid-area: name
      align-self: center

    &__price
      font-size: 1.5em
      font-weight: bold
      grid-area: price
      align-self: center
      justify-self: end

    &__delete-icon
      grid-area: delete
      align-self: center
      justify-self: center
      height: 30px
      cursor: pointer
</style>
