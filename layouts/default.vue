<template>
  <v-app dark>
    <TheHeader />
    <v-main>
      <Nuxt />
    </v-main>
    <TheFooter />
  </v-app>
</template>

<script>
export default {
  name: 'DefaultLayout',
  data() {
    return {}
  },
}
</script>
