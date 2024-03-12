<script>
import MainBlogComponent from "@/components/UI/MainBlogComponent.vue";
import HeaderComponent from "@/components/UI/HeaderComponent.vue";
import FooterComponent from "@/components/UI/FooterComponent.vue";
import ArticleFilterBlockComponent from "@/components/UI/ArticleFilterBlockComponent.vue";

export default {
  name: "BlogDetailsPageContent",
  data() {
    return {
      mainImg: {
        imgUrl: require('@/assets/img/blog_details_main.png'),
        isTitle: false,
        title:'',
        subtitle:'',
      },
    }
  },
  components: {ArticleFilterBlockComponent, FooterComponent, HeaderComponent, MainBlogComponent}
}
</script>

<template>
  <HeaderComponent/>
  <MainBlogComponent :mainImg="mainImg"/>
  <ArticleFilterBlockComponent/>
  <FooterComponent/>
</template>

<style scoped lang="scss">

</style>