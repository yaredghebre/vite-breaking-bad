<script >
import ContentCard from "./ContentCard.vue";
import AppLoader from "./AppHeader.vue";
import {store} from "../store";

export default {
    name: "AppMain",
    components: {
        ContentCard,
        AppLoader,
    },
    data() {
        return {
            store
        }
    }

}
</script>

<template>
    <main>
        <AppLoader v-if="store.loading" />
        <!-- <div class="container d-flex align-items-center p-5">
            <select name="" id="">
                <option value="">Alien</option>
                <option value="">Archfiend</option>
                <option value="">Melodious</option>
                <option value="">Noble Knight</option>
            </select>
        </div> -->

        <div class="container white p-5">
            <div class="container-title d-flex align-items-center">
                <h5 class="m-0 px-4">Found 39 cards</h5>
            </div>
            <div class="row row-cols-5">
                <div class="col mb-3" v-for="card in store.cards">
                    <ContentCard :card="card"/>
                </div>
            </div>
        </div>
    </main>
</template>

<style scoped lang="scss">
@use "../style/general.scss";
@use "../style/partials/variables" as *;

main {
    background-color: $primary_bg_color;
    padding: 50px 0;

    select {
        padding: 8px 100px 8px 10px;
        font-size: 1.3rem;
        border-radius: 10px;
    }

    .container {
        background-color: white;

        &-title {
            height: 60px;
            background-color: black;

            h5 {
                color: white;
            }
        }
    }
}

</style>
