<script setup>
import { ref, watch, watchEffect } from 'vue';
import TheContainer from '../components/TheContainer.vue';
const count = ref(1);
const res = ref();

watch(count, async (v) => {
    console.log("watch", v)
})

watchEffect(async () => {
    const response = await fetch(
        `https://jsonplaceholder.typicode.com/todos/${count.value}`
    )
    res.value = await response.json()
})
</script>

<template>
    <div class="context">
        <the-container>
            <h1> Test view </h1>
            <button @click="count++">Count: {{ count }}</button>
            <pre>{{ res }}</pre>
        </the-container>
    </div>
</template>

<style scoped>
.context {
    background: darkgray;
    min-height: 100vh;
}
</style>