<script setup>
import { ref } from 'vue';

const characters = 'ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789!@#$%^&*()_-+=<>?/\\|[]{};:.,';
const charactersLength = characters.length;
const length = 12;

// 生成されたパスワード
const generatedPassword = ref('');

const createRandomPassword = () => {
  let result = "";

  for (let i = 0; i < length; i++) {
    result += characters.charAt(Math.floor(Math.random() * charactersLength));
  }

  generatedPassword.value = result;
}

</script>

<template>
  <div class="row">
    <div class="col-md-10 col-md-offset-1">
      <h1>パスワード生成</h1>
      <div class="input-group mb-3">
        <input type="text" class="form-control" v-model="generatedPassword" />
        <button type="button" class="btn btn-outline-secondary" @click="createRandomPassword">パスワード生成</button>
      </div>
    </div>
  </div>
</template>

<style scoped>
</style>
