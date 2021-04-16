<template lang="pug">
.home
  .home-carousel
    .home-carousel__image
      img(src="@/assets/img/main-image-4.jpg")
    .home-carousel__text Simple kit for your own home-made hydroponics
    a.home-carousel__button(href="/products") SHOP
</template>

<script>
export default {}
</script>

<style lang="sass">
.home
  min-height: 84vh

  &-carousel

  &-carousel__image
    img
      position: relative
      object-fit: cover
      width: 100%
      height: 700px

  &-carousel__text
    position: absolute
    font-size: 2.25rem
    font-weight: 700
    color: white
    width: 400px
    text-align: center
    top: 15%
    left: 5%

  &-carousel__button
    width: 200px
    position: absolute
    top: 35%
    left: 10%
    border: 2px solid white
    color: white
    font-weight: 700
    border-radius: 50px
    padding: 16px 20px
    display: block
    text-align: center

  &-carousel__button:hover
    background-color: white
    color: #5664b9
</style>
