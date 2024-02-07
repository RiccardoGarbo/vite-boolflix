<script>
export default {
    name: 'AppHeader'
}
</script>
<template>
    <div id="header" class=" d-flex justify-content-between align-items-center">
        <h1>BOOLFLIX</h1>
        <div>

        </div>
        <form class="d-flex gap-3 align-items">
            <div class="mb-3 ">
                <input type="email" class="form-control">
            </div>
            <button type="submit" class="btn btn-primary">Cerca</button>
        </form>

    </div>
</template>
<style lang="scss" scoped>
#header {
    height: 100px;
}
</style>