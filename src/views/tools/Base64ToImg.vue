<script setup lang="ts">
import { ref } from 'vue';

const base64 = ref('');
const result = ref('');
const handleTransform = () => {
  if (base64.value.indexOf("base64") != -1) {
    result.value = base64.value;
  } else if (base64.value.indexOf("data:image/jpeg;base64") == -1) {
    result.value =  "data:image/jpeg;base64," + base64.value;
  } else if (base64.value.indexOf("data:image/png;base64") == -1) {
    result.value =  "data:image/png;base64," + base64.value;
  } else if (base64.value.indexOf("data:image/gif;base64") == -1) {
    result.value =  "data:image/gif;base64," + base64.value;
  }
}
const handleClear = () => {
  base64.value = '';
}

</script>

<template>
  <header class="header">
    <h1>Base64转图片</h1>
  </header>
  <main class="content">
    <textarea class="textarea" v-model="base64"></textarea>
    <div class="btns">
      <button @click="handleTransform">转换</button>
      <button @click="handleClear">清除</button>
    </div>
    <div class="result">
      <img :src="result" alt="">
    </div>
  </main>
</template>

<style lang="less">
.header {

}
.content {
  .textarea {
    width: 100%;
    height: 300px;
  }
  .btns {
    margin-top: 20px;
    button {
      margin-right: 10px;
      width: 100px;
      height: 40px;
    }
  }
  .result {
    margin-top: 20px;
    max-width: 800px;
    object-fit: contain;
  }
}
</style>
