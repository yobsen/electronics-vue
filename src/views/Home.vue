<template lang="pug">
.home
  .home__text Simple 3D-printed devices of your own choice. Show us your ideas and we'll create them together!
    router-link.home__button(to="/products") SHOP
</template>

<script>
export default {}
</script>

<style lang="sass">
.home
  min-height: 100vh
  background-image: url("~@/assets/img/soldering-iron.jpg")
  background-size: cover
  position: relative
  display: flex

  &__text
    font-size: 2rem
    font-weight: 700
    width: 700px
    color: white
    margin: auto auto
    text-align: center
    position: absolute
    top: 3%
    right: 2%

  &__button
    margin: 0 auto
    border: 2px solid white
    font-weight: 600
    border-radius: 50px
    margin-top: 20px
    padding: 16px 20px
    font-size: 28px
    display: block
    text-align: center
    color: white

  &__button:hover
    border: 2px solid #5664b9
    background-color: #5664b9
</style>
