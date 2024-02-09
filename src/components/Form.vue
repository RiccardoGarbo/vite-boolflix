<script>
export default {
    name: 'Appform',
    data: () => ({
        searchTitle: ''
    }),
    emits: ['submit-search', 'title-change'],
    props: {
        placeholder: String,
        buttonPh: String
    }

}
</script>
<template>
    <div id="form">
        <form @submit.prevent="$emit('submit-search', searchTitle)" class="d-flex gap-3 align-items-center">
            <div class="d-flex align-items-center ">
                <input :placeholder="placeholder" @keyup="$emit('title-change', searchTitle)" type="text"
                    class="form-control" v-model="searchTitle">
            </div>
            <button type="submit" class="btn btn-danger">{{ buttonPh }}</button>
        </form>
    </div>
</template>
<style lang="scss" scoped>
div #form {
    background: none;
}
</style>