<script setup>
import {RouterView, RouterLink} from "vue-router"
import {ref} from "vue"

const counter = ref(0)
</script>

<template>
  <main>
    <div class="links">
      <RouterLink active-class="active" to="/">Beranda</RouterLink>
      <RouterLink active-class="active" to="/about">Tentang</RouterLink>
    </div>
    <RouterView/>
  </main>
</template>

<style scoped>
.links {
  padding: 20px
}
.links a {
  margin: 0 5px
}

.active{
  font-weight: bold;
  color: black;
}
</style>