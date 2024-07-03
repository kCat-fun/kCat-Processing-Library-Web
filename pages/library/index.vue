<template>
    <div>
        <ContentDoc class="document" :path="path">
            <template #not-found>
                <p>ドキュメントが見つかりません</p>
                <p>指定されたパス（{{ path }}）にマークダウンファイルが存在しません。</p>
            </template>
        </ContentDoc>
    </div>
</template>

<script setup lang="ts">
  import { useRoute } from 'vue-router'
  
  const route = useRoute();
  const path = ref(route?.query?.path);
</script>

<style>
  .document {
    max-width: 800px;
    margin: 30px auto;
    line-height: 2rem;
  }

  .document h1 {
    margin: 30px 0;
    border-bottom: white 1px solid;
    color: #FAFAFA;
  }

  .document ul {
    margin-left: 20px;
  }

  .document h2 {
    margin-top: 10px;
    color: #FAFAFA;
  }

  .document a {
    color: #FAFAFA;
  }

  .document pre {
    background-color: #383832;
    padding: 15px;
    border-radius: 8px;
    line-height: 1.2rem;
  }
</style>