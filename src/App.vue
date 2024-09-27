<script setup>
import Navbar from "./components/Navbar.vue"
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <header>
    <div class="wrapper">
      <nav>
       <Navbar></Navbar>
      </nav>
    </div>
  </header>

  <RouterView />
</template>

<style>

</style>
