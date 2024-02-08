<script>
import Rating from './Rating.vue';
export default {
    name: `CardSerie`,
    components: { Rating },
    props: {
        serieTitle: String,
        serieOriginalTitle: String,
        serieVote: Number,
        serieLanguage: String,
        serieImage: String
    },
    data: () => ({ stringImg: 'https://image.tmdb.org/t/p/w342/' }),

    computed: {
        changeValueVote() {
            return Math.ceil(this.serieVote / 2)
        }
    }

}                                                           
</script>
<template>
    <h1>{{ serieTitle }}</h1>
    <h2>{{ serieOriginalTitle }}</h2>
    <Rating :rating="changeValueVote" />
    <div v-if="serieLanguage == 'en'">
        <img src="/img/en.png" :alt="serieLanguage">
    </div>
    <div v-else-if="serieLanguage == 'it'">
        <img src="/img/it.png" :alt="serieLanguage">
    </div>
    <div v-else>
        <img src="/img/mondo.jpg" alt="">
        <h5>Language:{{ serieLanguage }}</h5>
    </div>
    <img :src="stringImg + serieImage" :alt="serieTitle">
</template>
<style scoped></style>