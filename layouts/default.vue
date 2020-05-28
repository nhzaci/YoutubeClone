<template>
  <v-app dark>
    <NavBar />
    <nuxt />
  </v-app>
</template>

<script>
import NavBar from '../components/NavBar'

export default {
  components: {
    NavBar
  }
}
</script>
