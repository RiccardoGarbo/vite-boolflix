<script>
import axios from 'axios';
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
const endpointMovies = `https://api.themoviedb.org/3/search/movie?&api_key=18d004e7a15f51ac9c01ea83b056f7cb&language=it-IT&query=`
const endpointSeriesTv = `https://api.themoviedb.org/3/search/tv?&api_key=18d004e7a15f51ac9c01ea83b056f7cb&language=it-IT&query=`
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
    <AppHeader @search-title="searchProduction" @title-change="setTitle" />
    <AppMain />
</template>
<style></style>
