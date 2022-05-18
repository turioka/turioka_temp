<script setup>
import { ref } from "vue";

const items = ref([
  { name: "ここにやること", price: "ここにやるき", complish: true },
]);
const newItemName = ref("");
const newItemPrice = ref(0);

const addItem = () => {
  items.value.push({
    name: newItemName.value,
    price: newItemPrice.value,
    complish: false,
  });
};
const switching = (a) => {
  if (a.complish) {
    a.complish = false;
  } else {
    a.complish = true;
  }
};
</script>
<template>
  <div>
    <div>やることリスト</div>
    <div v-for="item in items" :key="item.name">
      <div class="item" :class="{ comp: item.complish }">
        <div class="name">名前: {{ item.name }}</div>
        <div class="price">{{ item.price }}</div>
        <button v-if="!item.complish" @click="switching(item)">完了？</button>
        <button v-if="item.complish" @click="switching(item)">完了！</button>
        <div><br /></div>
      </div>
    </div>
    <div>
      <label>
        やること
        <input v-model="newItemName" type="text" />
      </label>
      <label>
        記入時のやるき
        <input v-model="newItemPrice" type="number" />
      </label>
      <button @click="addItem()">add</button>
    </div>
  </div>
</template>
<style>
.comp {
  color: red;
}
</style>
