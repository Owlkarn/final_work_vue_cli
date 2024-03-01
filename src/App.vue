<template>
<div class="blog-details-page-content">
  <HeaderComponent/>
  <div class="blog-main blog-main-details"></div>
  <ArticleFilterBlockComponent/>
  <FooterComponent/>
</div>
</template>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

img {
  max-width: 100%;
}

a {
  text-decoration: none;
}
.center {
  padding-left: calc(50% - 600px);
  padding-right: calc(50% - 600px);
}

</style>
<script setup>
import HeaderComponent from "@/components/HeaderComponent.vue";
import ArticleFilterBlockComponent from "@/components/ArticleFilterBlockComponent.vue";
import FooterComponent from "@/components/FooterComponent.vue";
import '@/assets/fonts/stylesheet.css'
</script>