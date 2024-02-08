<script>
export default {
    name: `Card`,
    props: {
        production: Object,
    },
    data: () => ({ stringImg: 'https://image.tmdb.org/t/p/w342/' }),
    computed: {
        ratingCard() {
            return Math.ceil(this.production.vote_average / 2)
        }
    }

}

</script>
<template>
    <h1>{{ production.title || production.name }}</h1>
    <h2>{{ production.original_title || production.original_name }}</h2>
    <h3>{{ ratingCard }}</h3>
    <div v-if="production.original_language == 'en'">
        <img src="/img/en.png" :alt="production.original_language">
    </div>
    <div v-else-if="production.original_language == 'it'">
        <img src="/img/it.png" :alt="production.original_language">
    </div>
    <div v-else>
        <img src="/img/mondo.jpg" alt="">
        <h5>Language:{{ production.original_language }}</h5>
    </div>
    <img :src="stringImg + production.poster_path" :alt="production.title || production.name">
</template>
<style scoped></style>