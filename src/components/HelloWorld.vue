<script setup>
import { ref } from "vue";
import ClickCounter from "./ClickCounter.vue";
import ItemList from "./Itemlist.vue";

defineProps({
  msg: { type: String, default: "" },
});
</script>

<template>
  <div>
    <h1>{{ msg }}</h1>
    <ClickCounter />
    <ItemList />
  </div>
</template>

<style scoped>
a {
  color: #42b983;
}
</style>
