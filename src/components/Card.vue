<script>
import RatingStars from './RatingStars.vue';
export default {
    name: `Card`,
    components: { RatingStars },
    props: {
        production: Object,

    },

    data: () => ({
        stringImg: 'https://image.tmdb.org/t/p/w342/',
        placeholderImg: `https://www.altavod.com/assets/images/poster-placeholder.png`
    }),
    computed: {
        ratingCard() {
            return Math.ceil(this.production.vote_average / 2)
        },
        imgSrc() {
            if (this.production.poster_path === null) return this.placeholderImg
            return this.stringImg + this.production.poster_path
        }
    }

}
</script>
<template>
    <div class="card border-0 ">
        <img :src="imgSrc" :alt="production.title || production.name">
        <div id="info-card">
            <h4>Titolo:{{ production.title || production.name }}</h4>
            <h4>Titolo Originale:{{ production.original_title || production.original_name }}</h4>
            <RatingStars :rating="ratingCard" />
            <div v-if="production.original_language == 'en'">
                <img class="langimg" src="/img/en.png" :alt="production.original_language">
            </div>
            <div v-else-if="production.original_language == 'it'">
                <img class="langimg" src="/img/it.png" :alt="production.original_language">
            </div>
            <div v-else>
                <img class="langimg" src="/img/mondo.jpg" alt="">
                <h5>Lingua:{{ production.original_language }}</h5>
            </div>
        </div>
    </div>
</template>
<style scoped>
.card {
    position: relative;
}

#info-card {
    color: white;
    display: none;
    position: absolute;
    background-color: rgba(0, 0, 0, 0.75);
    height: 100%;
    width: 100%;
}

.card:hover #info-card {
    display: inline-block;
}

.langimg {
    width: 50px;
    height: 50px
}
</style>