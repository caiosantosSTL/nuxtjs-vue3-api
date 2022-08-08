<script setup>
import { RouterLink, RouterView } from "vue-router";
import HelloWorld from "@/components/HelloWorld.vue";
</script>

<template>
  <header>
    <nav class="nav-a">
      <RouterLink class="btn-nav" to="/">Home</RouterLink>
      <RouterLink class="btn-nav" to="/about">About</RouterLink>
    </nav>
  </header>

  <RouterView />

  <footer>footer</footer>
</template>

<style lang="sass">
/* @import '@/assets/base.css'; */

@import './assets/styleApp.sass'

template
  padding: 0
  margin: 0px

</style>
