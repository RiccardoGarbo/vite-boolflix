<script>
import axios from 'axios';
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
const endpointMovies = `https://api.themoviedb.org/3/search/movie?query=lupin&api_key=18d004e7a15f51ac9c01ea83b056f7cb&languate =it-IT`
import { store } from './data/store'
import 'bootstrap/dist/css/bootstrap.min.css';
export default {
    components: { AppHeader, AppMain },
    data: () => ({
        store
    }),
    computed: {
        serchMovies() {
            axios.get(endpointMovies).then(res => {
                store.movies = res.data.results
            })
        }

    },
    created() {
        this.serchMovies

    }


}

</script>

<template>
    <AppHeader />
    <AppMain />
</template>
<style></style>
