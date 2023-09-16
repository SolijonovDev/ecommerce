<script setup>
import { onMounted, inject } from 'vue';
import { useRouter, useRoute } from 'vue-router';

import Container from '../components/Container.vue';

onMounted(() => {
  console.log('login page mounted', Date.now());
});

const router = useRouter();
const route = useRoute();

const text = inject('text');
</script>

<template>
  <div>
    <Container class="container">
      <div class="content">
        <h2 class="title">Login page</h2>
      <div class="block">
         <button>Login with Google</button>
         <button>Login with Facebook</button>
         <button>Login with Github</button>
      </div>
      </div>
    </Container>
  </div>
</template>

<style scoped lang="scss">
 .container{
  display: flex;
  justify-content: center;
  padding-top: 60px;
 }
 .content{
  width: 100%;
  max-width: 450px;
  padding: 15px;
  border-radius: 8px;
 }
 .title{
  text-align: center;
  margin-bottom: 25px;
 }
 .block{
  margin-bottom: 15px;

  button{
    margin-bottom: 20px;
    padding: 15px;
    width: 100%;
    display: block;
    border-radius: 8px;
    font-size: 18px;
    font-weight: 500;
  }
 }
</style>
