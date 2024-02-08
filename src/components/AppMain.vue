<script>
import { store } from '../data/store'
import CardMovie from './CardMovie.vue';
import CardSerie from './CardSerie.Vue';
export default {
    name: 'AppMain',
    components: { CardMovie, CardSerie },
    data: () => ({
        store
    }),

}
</script>
<template>
    <section id="movies">
        <h1 class="text-danger">MOVIES</h1>
        <div v-for="movie in store.movies">
            <CardMovie :movieTitle="movie.title" :movieOriginalTitle="movie.original_title" :movieVote="movie.vote_average"
                :movieLanguage="movie.original_language" :movieImage="movie.poster_path" />
        </div>
    </section>
    <section id="Series-tv">
        <h1>SERIES</h1>
        <div v-for="serie in store.SeriesTv">
            <CardSerie :serieTitle="serie.name" :serieOriginalTitle="serie.original_name" :serieVote="serie.vote_average"
                :serieLanguage="serie.original_language" :serieImage="serie.poster_path" />
        </div>
    </section>
</template>
<style scoped>
img {
    width: 100px;
    height: auto
}
</style>