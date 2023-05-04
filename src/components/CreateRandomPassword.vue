<script setup>
import { ref } from 'vue';

// パスワードの元になる文字列
const characters = 'ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789!@#$%^&*()_-+=<>?/\\|[]{};:.,';

// パスワードの文字数
const wordCount = ref(12);

// 生成されたパスワード
const generatedPassword = ref('');

const createRandomPassword = () => {
  let result = "";

  for (let i = 0; i < wordCount.value; i++) {
    result += characters.charAt(Math.floor(Math.random() * characters.length));
  }

  generatedPassword.value = result;
}

</script>

<template>
  <div class="row">
    <div class="col-md-10 col-md-offset-1">
      <h1>パスワード生成</h1>
      <form class="row g-3 align-items-center">
        <div class="col-sm-1">
          <input type="text" class="form-control" v-model="wordCount" />
        </div>
        <div class="col-sm-7">
          <input type="text" class="form-control" v-model="generatedPassword" />
        </div>
        <div class="col-sm-2">
          <button type="button" class="btn btn-outline-secondary" @click="createRandomPassword">パスワード生成</button>
        </div>
      </form>
    </div>
  </div>
</template>

<style scoped>
</style>
