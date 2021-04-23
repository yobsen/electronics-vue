<template lang="pug">
.sign-up
  .sign-up-form
    .sign-up-form__title Join us!
    input.sign-up-form__input(placeholder="Email" v-model="user.email")
    input.sign-up-form__input(placeholder="Password" v-model="user.password")
    .sign-up-form__button Sign Up
</template>

<script>
export default {
  data() {
    return {
      user: {
        email: "",
        password: ""
      }
    }
  }
}
</script>

<style lang="sass">
.sign-up
  min-height: 70vh
  display: flex
  justify-content: center
  align-items: center

  .sign-up-form
    width: 400px
    display: flex
    flex-direction: column
    justify-content: center
    align-items: center

    &__title
      font-size: 1.25em
      font-weight: bold

    &__input
      color: #5664b9
      border: 2px solid #5664b9
      border-radius: 8px
      placeholder-color: #5664b9
      padding: 16px
      margin: 20px 0
      width: 100%

      &::placeholder
        color: #5664b9
        font-size: 1.25em

    &__button
      border: 2px solid #5664b9
      font-weight: 600
      border-radius: 50px
      padding: 10px
      font-size: 1.25em
      display: block
      text-align: center
      width: 200px
      margin-top: 10px
      cursor: pointer

    &__button:hover
      color: white
      border: 2px solid white
      background-color: #5664b9
</style>
