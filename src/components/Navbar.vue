<template>
  <nav class="navbar">
    <RouterLink class="nav-link" to="/">Početna</RouterLink>
    <RouterLink class="nav-link" to="/about">O nama</RouterLink>
    <RouterLink class="nav-link" to="/contact">Kontaktiraj nas</RouterLink>
  </nav>
</template>

<script>
import { RouterLink } from 'vue-router'
export default {}
</script>

<style scoped>
.navbar {
  background-color: white;
  position: sticky;
  top: 0;
  width: 100%;
  display: flex;
  justify-content: center; /* Adjust as needed */
  align-items: center;
  height: 80px; /* Adjust as needed */
  background-color: var(--main-bg-clr);

}

.nav-link {
  text-decoration: none;
  color: white;
  padding: 10px 20px; /* Adjust padding as needed */
  margin: 0 10px; /* Adjust margin between links as needed */
  transition: background-color 0.3s;
}

.nav-link:hover {
  background-color: #ddd; /* Add a background color on hover if desired */
}
</style>
