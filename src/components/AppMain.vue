<script >
import ContentCard from "./ContentCard.vue";
import AppLoader from "./AppLoader.vue";
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
      <div v-else>
        <div>
          <div class="container white p-5">
            <div class="container-title d-flex align-items-center">
              <h5 class="m-0 px-4">Found {{ store.cards.length }} cards</h5>
            </div>

            <div class="row row-cols-5">
              <div class="col mb-3" v-for="card in store.cards" :key="card.id">
                <ContentCard :card="card" />
              </div>
            </div>
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
