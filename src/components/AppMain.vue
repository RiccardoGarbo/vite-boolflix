<script>
import { store } from '../data/store'
export default {
    name: 'AppMain',
    data: () => ({
        store
    })
}
</script>
<template>
    <section id="movies">
        <h1 class="text-danger">MOVIES</h1>
        <div v-for="movie in store.movies">
            <h1>{{ movie.title }}</h1>
            <h2>{{ movie.original_title }}</h2>
            <h4>{{ movie.vote_average }}</h4>

            <div v-if="movie.original_language == 'en'">
                <img src="../../public/img/en.png" :alt="movie.original_language">
            </div>
            <div v-else-if="movie.original_language == 'it'">
                <img src="../../public/img/it.png" :alt="movie.original_language">
            </div>
            <div v-else>
                <img src="../../public/img/mondo.jpg" alt="">
                <h5>Language:{{ movie.original_language }}</h5>
            </div>
        </div>
    </section>
    <section id="Series-tv">
        <h1>SERIES</h1>
        <div v-for="serie in store.SeriesTv">
            <h1>{{ serie.name }}</h1>
            <h2>{{ serie.original_name }}</h2>
            <h4>{{ serie.vote_average }}</h4>

            <div v-if="serie.original_language == 'en'">
                <img src="../../public/img/en.png" :alt="serie.original_language">
            </div>
            <div v-else-if="serie.original_language == 'it'">
                <img src="../../public/img/it.png" :alt="serie.original_language">
            </div>
            <div v-else>
                <img src="../../public/img/mondo.jpg" alt="">
                <h5>Language:{{ serie.original_language }}</h5>
            </div>
        </div>

    </section>
</template>
<style scoped>
img {
    width: 100px;
    height: auto
}
</style>