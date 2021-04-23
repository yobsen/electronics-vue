<template lang="pug">
component(:is="layout" id="app")
  router-view
</template>

<script>
import User from "./layouts/User.vue"
// import Admin from "./layouts/Admin.vue"
export default {
  name: "App",
  components: { User },
  computed: {
    layout() {
      return "User"
    }
  }
}
</script>

<style lang="sass">
@import "./assets/styles/fonts"

body
  font-family: IBMPlexMono
  color: #5664b9
  font-size: 18px

a
  text-decoration: none
  outline: 0
  color: inherit

input
  outline: 0

#app
  min-height: 100vh
</style>
