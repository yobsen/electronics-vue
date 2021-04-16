<template lang="pug">
.product-form
  .product-form__input
    input(v-model="product.name" placeholder="Name")
  .product-form__input
    input(v-model="product.desc" placeholder="Description")
  .product-form__input
    input(v-model="product.centi_price" placeholder="Price")
  .product-form__save-button-container
    .product-form__save-button(@click="createProduct") Save
</template>

<script>
export default {
  data() {
    return {
      product: {
        name: "",
        desc: "",
        centi_price: "",
        is_active: false,
        image_url: ""
      }
    }
  }
  // methods: {
  //   async createProduct() {
  //     await this.$store.dispatch("product/createProduct", this.product)
  //   }
  // }
}
</script>

<style lang="sass">
.product-form
  &__input, &__save-button-container
    display: flex
    justify-content: center
    padding-top: 1.5em

    input
      width: 20em

  &__save-button
    width: 18em
    border: 2px solid #5664b9
    font-weight: 700
    border-radius: 50px
    padding: 0.75em 1em
    display: block
    text-align: center

  &__save-button:hover
    color: white
    background-color: #5664b9
    cursor: pointer
</style>
