<template>
  <v-app dark>
    <NavBar />
    <v-content>
      <nuxt />
    </v-content>
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
