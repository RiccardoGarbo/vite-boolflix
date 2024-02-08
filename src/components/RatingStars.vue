<script>
export default {
    name: 'Rating',
    data: () => ({
        maxRating: 5
    }),
    props: {
        rating: Number
    }
}
</script>
<template>
    <div class="rating">
        <span v-for="i in rating" :key="i">
            <i class="fa-solid fa-star"></i></span>
        <span v-for="i in maxRating - rating" :key="i"><i class="fa-regular fa-star"></i></span>
    </div>
</template>
<style></style>
<style></style>