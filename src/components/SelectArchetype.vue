<script>
import { store } from "../store";

export default {
    name: "SelectArchetype",
    emits: ["filter"],
    data() {
        return {
            store,
            archetypeOptions: ["Alien", "Ally of Justice", "Ancient of Gear"]
        }
    }
}
</script>

<template>
    <div class="container mb-3">
        <select v-model="store.selectedOption" @change="$emit('filter')" class="form-select w-25 " name="archetype" id="archetype">
            <option value="">All</option>
            <option :value="archetype" v-for="archetype in archetypeOptions">{{ archetype }}</option>
        </select>
    </div>
</template>

