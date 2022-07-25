<template>
  <v-app-bar
    color="accent"
    elevation="0"
    height="70"
    min-height="70"
    dark
    app
    class="px-md-5 px-0"
  >
    <v-toolbar-title class="fw-4">
      <a href="#" class="decoration-none white--text"> Capslock Studio </a>
    </v-toolbar-title>

    <v-spacer></v-spacer>
    <div class="d-flex align-self-center nav-md">
      <a href="#home" class="white--text decoration-none">
        <v-btn text tile class="text-capitalize"> Home </v-btn></a
      >
      <a href="#work" class="white--text decoration-none">
        <v-btn text tile class="text-capitalize"> Work </v-btn></a
      >
      <a href="#skills" class="white--text decoration-none">
        <v-btn text tile class="text-capitalize"> Skills </v-btn></a
      >
      <a href="#testimonials" class="white--text decoration-none">
        <v-btn text tile class="text-capitalize"> Reviews </v-btn></a
      >
      <a href="#contact" class="white--text decoration-none">
        <v-btn text tile class="text-capitalize"> Contact </v-btn></a
      >
    </div>
    <div class="nav-sm">
      <v-menu offset-y left>
        <template #activator="{ on, attrs }">
          <v-btn icon v-bind="attrs" v-on="on">
            <v-icon> mdi-menu </v-icon>
          </v-btn>
        </template>
        <v-list>
          <v-list-item>
            <a href="#home" class="white--text decoration-none w-100">
              <v-btn text block tile class="text-capitalize"> Home </v-btn></a
            >
          </v-list-item>
          <v-list-item>
            <a href="#work" class="white--text decoration-none w-100">
              <v-btn text block tile class="text-capitalize"> Work </v-btn></a
            >
          </v-list-item>
          <v-list-item>
            <a href="#skills" class="white--text decoration-none w-100">
              <v-btn text block tile class="text-capitalize"> Skills </v-btn></a
            >
          </v-list-item>
          <v-list-item>
            <a href="#testimonials" class="white--text decoration-none w-100">
              <v-btn text block tile class="text-capitalize">
                Reviews
              </v-btn></a
            >
          </v-list-item>
          <v-list-item>
            <a href="#contact" class="white--text decoration-none w-100">
              <v-btn text block tile class="text-capitalize">
                Contact
              </v-btn></a
            >
          </v-list-item>
        </v-list>
      </v-menu>
    </div>
  </v-app-bar>
</template>
<style lang="scss">
.nav-sm {
  display: none;
}
@media screen and (max-width: 610px) {
  .nav-md.d-flex {
    display: none !important;
  }
  .nav-sm {
    display: flex;
  }
}
</style>
