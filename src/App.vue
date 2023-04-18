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
    this.store.loading = true;
    axios.get(store.apiURL).then((resp) => {
      console.log(resp.data.data);
      this.store.cards = resp.data.data;
      this.store.loading = false;
    })
  },
  methods: {
    handleFilter() {
      axios.get(store.apiURL, {
        params: {
          archetype: this.store.selectedOption
        }
      }).then((resp) => {
        console.log(resp.data.data);
        this.store.cards = resp.data.data;
      })
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
