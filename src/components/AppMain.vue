<script>
import { store } from '../data/store'
import Card from './Card.vue';
export default {
    name: 'AppMain',
    components: { Card },
    data: () => ({
        store
    }),

}
</script>
<template>
    <section id="movies">
        <h1 class="text-danger">MOVIES</h1>
        <Card v-for="movie in store.movies" :key="movie.id" :production="movie" />
    </section>
    <section>
        <h2>Series</h2>
        <Card v-for="serie in store.seriesTv" :key="serieTv.id" :production="serie" />
    </section>
</template>
<style scoped>
img {
    width: 100px;
    height: auto
}
</style>