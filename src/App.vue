<script>
import axios from 'axios';
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import { store } from './data/store'
import { api } from './data/index'
import 'bootstrap/dist/css/bootstrap.min.css';
export default {
    components: { AppHeader, AppMain },
    data: () => ({
        store,
        title: ''
    }),
    methods: {
        setTitle(title) {
            this.title = title
        },
        searchProduction() {
            this.fetchApi('/search/movie', 'movies')
            this.fetchApi('/search/tv', 'seriesTv')
        },

        fetchApi(endpoint, library) {
            const { baseUri, apiKey, language } = api
            const params = {
                query: this.title,
                api_key: apiKey,
                language
            }
            axios.get(`${baseUri}${endpoint}`, { params }).then(res => {
                store[library] = res.data.results
            })
        },
    },



}

</script>

<template>
    <div class="vh-100">
        <AppHeader @search-title="searchProduction" @title-change="setTitle" />
        <AppMain />
    </div>
</template>
<style lang="scss">
div {
    background-image: url('../public/img/Netflix-Gradient-HD-Wallpaper-7281.png');
}
</style>
