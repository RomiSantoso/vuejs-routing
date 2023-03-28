<script setup>
import {useRoute, RouterView, useRouter} from 'vue-router'
import {ref, onBeforeMount} from "vue"
import cars from "../data.json"

const car = ref(null)
const route = useRoute()
const {id} = route.params
const router = useRouter()

onBeforeMount(() => {
    car.value = cars.find(c => c.id === parseInt(id))
})

</script>

<template>
    <div class="container">
        <div v-if="car">
            <h2>Detail Mobil</h2>
            <h1>{{ car.make }}</h1>
            <p>{{ car.body }}</p>
            <p>{{ car.price }}</p>
            <p>{{ car.year }}</p>
            <RouterView />
        </div>
        <div v-else>
            <p>Data mobil tidak ditemukan</p>
        </div>
        <button @click="router.back()">kembali</button>
    </div>
</template>

<style>
h2{
    margin-bottom: 2px;
}
</style>