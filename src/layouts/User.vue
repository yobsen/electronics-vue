<template lang="pug">
.user-layout
  UserHeader
  router-view
  UserFooter
</template>

<script>
import UserHeader from "./user/Header"
import UserFooter from "./user/Footer"

export default {
  components: {
    UserHeader,
    UserFooter
  }
}
</script>

<style lang="sass">
.user-layout
  min-height: 100vh
</style>
