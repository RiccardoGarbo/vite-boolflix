<script>
import AppContent from './AppContent.vue';
import { store } from '../data/store'
export default {
    name: 'AppMain',
    components: { AppContent },
    data: () => ({
        store
    })

}
</script>
<template>
    <div class="container">
        <AppContent v-if="this.store.movies.length || this.store.seriesTv.length >= 1" />
    </div>
</template>
<style scoped>
img {
    width: 100px;
    height: auto
}
</style>