<script >
export default {
    name: "AppHeader",
    props: {
        title: String
    }
}
</script>

<template>
    <header class="d-flex align-items-center px-3 gap-4">
        <img src="https://occ-0-2433-1001.1.nflxso.net/dnm/api/v6/LmEnxtiAuzezXBjYXPuDgfZ4zZQ/AAAABdpYalFU9SD9K6dNwu9SlKsNaQ3AIGWFrN_uDy6R7N3TS5DHIatIETtgeqwC0kM01zJyor2znGql_ixTWzVueA-GllV7Hn03ygETN_Nd7oZA.png?r=81f" alt="">
        <h1> {{ title }}</h1>
    </header>
</template>

<style scoped lang="scss">
@use "../style/general.scss";

header {
    height: 100px;
    width: 100%;
    background-color: white;

    img {
        height: 50%;
    }
}

</style>
