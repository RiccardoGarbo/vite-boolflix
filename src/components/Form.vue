<script>
export default {
    name: 'Appform',
    data: () => ({
        searchTitle: ''
    }),
    emits: ['submit-search']
}
</script>
<template>
    <form action="" @submit.prevent="$emit('submit-search', searchTitle)" class="d-flex gap-3 align-items">
        <div class="mb-3 ">
            <input type="text" class="form-control" v-model="searchTitle">
        </div>
        <button type="submit" class="btn btn-primary">Cerca</button>
    </form>
</template>
<style scoped></style>