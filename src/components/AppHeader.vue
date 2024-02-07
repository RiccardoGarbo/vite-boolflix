<script>
import Form from './Form.vue';
export default {
    name: 'AppHeader',
    components: { Form },
    emits: ['search-title']
}
</script>
<template>
    <div id="header" class=" d-flex justify-content-between align-items-center">
        <h1>BOOLFLIX</h1>
        <div>

            <Form @submit-search="$emit('search-title', $event)" />
        </div>

    </div>
</template>
<style lang="scss" scoped>
#header {
    height: 100px;
}
</style>