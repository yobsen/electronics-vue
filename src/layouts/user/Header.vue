<template lang="pug">
.user-header
  .user-header__container
    a.user-header__logo(href="/")
      img.user-header__logo-icon(src="@/assets/img/logo.png")
      .user-header__logo-name HYDROPONICS
    .user-header__links
      a.user-header__link(href="/products") SHOP
      a.user-header__link SUPPORT
      a.user-header__link CONTACT
    .user-header__user-actions
      img.user-header__user-icon(src="@/assets/img/user-icon.svg")
      img.user-header__cart-icon(src="@/assets/img/shopping-cart.svg")
</template>

<style lang="sass">
.user-header
  position: sticky
  top: 0
  z-index: 2
  border-bottom: 1px solid #E5E5E5
  background-color: white

  &__container
    display: flex
    justify-content: space-between
    align-items: center
    padding: 0px 1.875em 0.3125em 1.875em

  &__logo
    display: flex
    align-items: center

  &__logo-icon
    max-height: 50px
    padding: 0.3125em

  &__logo-name
    font-family: Notable
    font-weight: 700
    font-size: 1.75rem
    color: #5664b9

  &__links
    font-weight: 700
    display: flex
    align-items: center
    padding-right: 6.875em
    cursor: pointer
    height: 60px

  &__link
    padding-right: 5em
    color: #5664b9

  &__link:hover
    color: #1a2c54

  &__user-actions
    display: flex

  &__user-icon
    height: 20px
    padding-right: 1.875em

  &__cart-icon
    max-height: 30px
</style>
