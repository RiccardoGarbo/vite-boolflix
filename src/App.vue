<script>
import axios from 'axios';
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
const endpoint = `https://api.themoviedb.org/3/search/movie?&api_key=18d004e7a15f51ac9c01ea83b056f7cb&languate =it-IT&query=`
import { store } from './data/store'
import 'bootstrap/dist/css/bootstrap.min.css';
export default {
    components: { AppHeader, AppMain },
    data: () => ({
        store
    }),
    computed: {
        searchMovies() {
            axios.get(endpoint).then(res => {
                store.movies = res.data.results
            })
        }
    },
    methods: {
        searchTitle(title) {
            axios.get(endpoint + `${title}`).then(res => {
                store.movies = res.data.results
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
