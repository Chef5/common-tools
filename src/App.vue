<script setup lang="ts">
import { RouterView, useRouter } from 'vue-router';
import LeftMenu from './views/LeftMenu.vue';

const router = useRouter();
const goHome = () => {
  router.replace('/');
}

</script>

<template>
  <header>
    <img alt="Vue logo" class="logo" src="@/assets/logo.svg" width="125" height="125" @click="goHome" />
    <div class="wrapper">
      <LeftMenu></LeftMenu>
    </div>
  </header>

  <main class="main">
    <RouterView />
  </main>
</template>

<style scoped>
header {
  padding: 10px;
  line-height: 1.5;
  max-height: 100vh;
  width: 150px;
}
.main {
  flex: 1;
  padding: 10px;
}

</style>
