<script>
import HeaderComponent from "@/components/UI/HeaderComponent.vue";
import FooterComponent from "@/components/UI/FooterComponent.vue";
import MainBlogComponent from "@/components/UI/MainBlogComponent.vue";
import LatestPostComponent from "@/components/UI/LatestPostComponent.vue";
import ArticlesAndNewsComponent from "@/components/UI/ArticlesAndNewsComponent.vue";
import PageButtons from "@/components/UI/PageButtons.vue";

export default {
  name: "BlogPageComponent",
  data() {
    return {
      mainImg: {
        imgUrl: require('@/assets/img/articles-main.png'),
        isTitle: true,
        title:'Articles & News',
        subtitle:'Home / Blog',
      },
      latestPostData: {
        img: require('@/assets/img/latest-post.png'),
        title: 'Low Cost Latest Invented Interior Designing Ideas',
        textFirst: 'Lorem ipsum dolor sit amet, adipiscing Aliquam eu sem vitae turpis dignissim maximus.posuere in.Contrary to popular belief.',
        textSecond: 'Lorem Ipsum is not simply random text. It has roots in a piece of classica.'
      },
      articlesAndNewsData: {
        isSubtitle: false,
        numberOfTitles: 0,
        titleAlign: 'left',
      }
    }
  },
  components: {
    PageButtons,
    ArticlesAndNewsComponent, LatestPostComponent, MainBlogComponent, FooterComponent, HeaderComponent}
}
</script>

<template>
  <HeaderComponent/>
  <MainBlogComponent :mainImg="mainImg"/>
  <LatestPostComponent :latestPostData="latestPostData"/>
  <ArticlesAndNewsComponent :articlesAndNewsData="articlesAndNewsData"/>
  <PageButtons/>
  <FooterComponent/>
</template>

<style scoped lang="scss">

</style>