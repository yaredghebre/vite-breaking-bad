<script >
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import axios from "axios";
import { store } from "./store";
import SelectArchetype from './components/SelectArchetype.vue';


export default {
  components: {
    AppHeader,
    AppMain,
    SelectArchetype
},
  data() {
    return {
      store
    }
  },
  mounted() {
    this.getCards();
  },
  methods: {
    getCards() {
      // this.store.loading = true;
      const params = {};
      if(this.store.selectedOption) {
        params.archetype = this.store.selectedOption;
      }
      axios.get(this.store.apiURL, {
        params
      }).then(resp => {
        this.store.cards = resp.data.data;
      })
    },
    handleFilter() {
      this.getCards();
    }
  }
}
</script>

<template>
  <AppHeader title="Yu-Gi-Oh Api" />
  <SelectArchetype @filter="handleFilter"/>
  <AppMain />
</template>

<style lang="scss">
@use "./style/general.scss";

</style>
