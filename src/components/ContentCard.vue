<script>
export default {
    name: "ContentCard",
    props: {
        card: Object
    }
}
</script>

<template>
    <div class="card-box text-center d-flex flex-column justify-content-between">
        <img :src="card.card_images[0].image_url_small" alt="">
        <h5 class="mb-3">{{ card.name.toUpperCase() }}</h5>
        <p>{{ card.archetype }}</p>
    </div>
</template>

<style scoped lang="scss">
@use "../style/partials/variables" as *;

.card-box {
    background-color: $primary_bg_color;
    height: 100%;

    h5 {
        color: white;
    }
}

</style>