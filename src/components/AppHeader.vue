<script>
import Form from './Form.vue';
export default {
    name: 'AppHeader',
    components: { Form }
}
</script>
<template>
    <div id="header" class=" d-flex justify-content-between align-items-center">
        <h1>BOOLFLIX</h1>
        <div>

            <Form />
        </div>

    </div>
</template>
<style lang="scss" scoped>
#header {
    height: 100px;
}
</style>