<template lang="pug">
.user-header
  .user-header__container
    router-link.user-header__logo(to="/")
      img.user-header__logo-icon(src="@/assets/img/logo.png")
      .user-header__logo-name ELECTRONICS
    .user-header__links
      router-link.user-header__link(to="/products") SHOP
      a.user-header__link SUPPORT
      a.user-header__link CONTACT
    .user-header__user-actions
      router-link(to="/sign-up")
        img.user-header__user-icon(src="@/assets/img/user-icon.svg")
      router-link(to="/cart")  
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
    color: #bc75f9
    margin-top: -5px

  &__links
    font-weight: 700
    display: flex
    align-items: center
    padding-right: 6.875em
    cursor: pointer
    height: 60px

  &__link
    padding-right: 5em
    color: #bc75f9

  &__link:hover
    color: #9b42e9

  &__user-actions
    display: flex

  &__user-icon
    height: 20px
    padding-right: 1.875em

  &__cart-icon
    max-height: 30px
</style>
