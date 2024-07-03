<!-- pages/index.vue -->
<template>
  <div>
    <h1>kCat's Processingライブラリ</h1>
    <div v-for="item in items" class="lib-card">
      <NuxtLink :to="'/library?path=' + item.link" class="link">
        <div class="content-box">
          <h2>{{ item.name }}</h2>
          <p>{{ item.explanation }}</p>
        </div>
        <div class="image-box">
          <img :src="item.image" alt="">
        </div>
      </NuxtLink>
    </div>
  </div>
</template>

<script setup>
import contentList from '~/content/contents.json';
const items = ref(contentList.content)
console.log(items.value)
</script>

<style scoped>
  h1 {
    text-align: center;
    margin: 30px auto;
  }

  .lib-card {
    max-width: 350px;
    margin: 20px auto;
    background-color: #404040;
    border-radius: 10px;
  }

  h2 {
    margin-bottom: 10px;
    border-bottom: 1px solid white;
  }

  .lib-card:hover {
    cursor: pointer;
  }

  .link {
    height: 100%;
    width: 100%;;
    text-decoration: none;
    color: #FAFAFA;
  }

  @media screen and (min-width: 800px) {
    .lib-card {
      max-width: 800px;
      height: 300px;
    }

    .link {
      display: flex;
    }
  }

  .content-box {
    margin: auto 20px;
    width: auto;
    height: 250px;
  }

  .image-box {
    margin: auto 20px auto 0;
    width: auto;
    height: 250px;
  }
  
  img {
    border-radius: 10px;
    width: auto;
    height: 250px;
  }
</style>