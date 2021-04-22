<template lang="pug">
.home
  .home__text Simple 3D-printed devices of your own choice. Show us your ideas and we'll create them together!
    a.home__button(href="/products") SHOP
</template>

<script>
export default {}
</script>

<style lang="sass">
.home
  min-height: 70vh

  &__text
    margin-top: 200px
    font-size: 2.25rem
    font-weight: 700
    width: 980px
    margin: 200px auto
    text-align: center

  &__button
    margin: 0 auto
    border: 2px solid #5664b9
    font-weight: 600
    border-radius: 50px
    margin-top: 20px
    padding: 16px 20px
    font-size: 28px
    display: block
    text-align: center

  &__button:hover
    color: white
    border: 2px solid white
    background-color: #5664b9
</style>
