<script>
import axios from 'axios';
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
const endpointMovies = `https://api.themoviedb.org/3/search/movie?&api_key=18d004e7a15f51ac9c01ea83b056f7cb&language=it-IT&query=`
const endpointSeriesTv = `https://api.themoviedb.org/3/search/tv?&api_key=18d004e7a15f51ac9c01ea83b056f7cb&language=it-IT&query=`
import { store } from './data/store'
import 'bootstrap/dist/css/bootstrap.min.css';
export default {
    components: { AppHeader, AppMain },
    data: () => ({
        store
    }),
    methods: {
        searchTitle(title) {
            axios.get(endpointMovies + `${title}`).then(res => {
                store.movies = res.data.results
            })
            axios.get(endpointSeriesTv + `${title}`).then(res => {
                store.SeriesTv = res.data.results
            })
        },
    },




}

</script>

<template>
    <AppHeader @search-title="searchTitle" />
    <AppMain />
</template>
<style></style>
