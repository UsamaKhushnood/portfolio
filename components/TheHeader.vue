<template>
  <v-app-bar
    color="accent"
    elevation="0"
    height="70"
    min-height="70"
    dark
    app
    class="px-5"
  >
    <v-toolbar-title class="fw-4">Capslock Studio</v-toolbar-title>

    <v-spacer></v-spacer>
    <div class="d-flex align-self-center">
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
  </v-app-bar>
</template>
