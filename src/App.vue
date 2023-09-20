<script setup>
import { useRouter } from "vue-router";
import { onMounted } from "vue";
import MainLayout from "./layouts/MainLayout.vue";
import { useCounterStore } from "./stores/counter";

const counter = useCounterStore();

counter.count++;
// with autocompletion ✨
counter.$patch({ count: counter.count + 1 });
// or using an action instead
counter.increment();

const router = useRouter();

onMounted(() => {
  router.push("/test");
})
</script>

<template>
  <!-- <MainLayout> -->
  <router-view />
  <!-- <div>Current Count: {{ counter.count }}</div> -->
  <!-- <button @click="counter.increment">click</button> -->
  <!-- </MainLayout> -->
</template>

<style scoped></style>
