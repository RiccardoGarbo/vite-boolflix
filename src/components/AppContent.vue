<script>
import Card from './Card.vue';
import { store } from '../data/store'
export default {
    name: 'AppContent',
    components: { Card },
    data: () => ({
        store
    }),


}
</script>
<template>
    <section>
        <h1>MOVIE</h1>
        <div class="d-flex flex-wrap">
            <Card class="s-card" v-for="movie in store.movies" :key="movie.id" :production="movie" />
        </div>
    </section>
    <section>
        <h1>SERIES</h1>
        <div class="d-flex flex-wrap">
            <Card class="s-card" v-for="serie in store.seriesTv" :key="serie.id" :production="serie" />
        </div>
    </section>
</template>
<style scoped>
.s-card {
    flex-basis: 25%;

}
</style>


