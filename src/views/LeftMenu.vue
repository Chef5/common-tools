<script setup lang="ts">
import { ref } from 'vue';
import { RouterLink, RouterView } from 'vue-router'

const tools = ref([
  {
    id: 1,
    title: 'Base转图片',
    view: '/base64-img',
  }
]);

</script>

<template>
  <nav>
    <div
      class="menu"
      v-for="tool of tools"
      :key="tool.id"
    >
      <RouterLink :to="tool.view">{{ tool.title }}</RouterLink>
    </div>
  </nav>
</template>

<style>
a {
  padding: 6px 3px;
  border-bottom: 1px solid #999;
}
</style>