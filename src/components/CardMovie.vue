<script>
import Rating from './Rating.vue';
export default {
    name: `CardMovie`,
    components: { Rating },
    props: {
        movieTitle: String,
        movieOriginalTitle: String,
        movieVote: Number,
        movieLanguage: String,
        movieImage: String
    },
    data: () => ({ stringImg: 'https://image.tmdb.org/t/p/w342/' }),

    computed: {
        changeValueVote() {
            return Math.ceil(this.movieVote / 2)
        }
    }

}                                                           
</script>
<template>
    <h1>{{ movieTitle }}</h1>
    <h2>{{ movieOriginalTitle }}</h2>
    <Rating :rating="changeValueVote" />
    <div v-if="movieLanguage == 'en'">
        <img src="/img/en.png" :alt="movieLanguage">
    </div>
    <div v-else-if="movieLanguage == 'it'">
        <img src="/img/it.png" :alt="movieLanguage">
    </div>
    <div v-else>
        <img src="/img/mondo.jpg" alt="">
        <h5>Language:{{ movieLanguage }}</h5>
    </div>
    <img :src="stringImg + movieImage" alt="movieTitle">
</template>
<style scoped></style>