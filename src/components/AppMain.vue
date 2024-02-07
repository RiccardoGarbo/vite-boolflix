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
            <h5>{{ movie.original_language }}</h5>
            <hr>
        </div>
    </section>
</template>
<script></script>