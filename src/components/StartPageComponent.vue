<script>
import GetStartedComponent from "@/components/UI/MainPageStartComponent.vue";
import FollowProjectsComponent from "@/components/UI/FollowProjectsComponent.vue";
import StatisticComponent from "@/components/UI/StatisticComponent.vue";
import ArticlesAndNewsComponent from "@/components/UI/ArticlesAndNewsComponent.vue";
import HeaderComponent from "@/components/UI/HeaderComponent.vue";
import FooterComponent from "@/components/UI/FooterComponent.vue";

export default {
  name: "StartPageComponent",
  data() {
    return {
      mainPageStartedURL: require('@/assets/img/start_img.png'),
      followProjectsData: [
        {
          name: 'Modern Kitchen',
          text:'Decor / Architecture',
          imgUrl: require('@/assets/img/project_1.png')
        },
        {
          name: 'Modern Kitchen',
          text:'Decor / Architecture',
          imgUrl: require('@/assets/img/project_2.png')
        },
        {
          name: 'Modern Kitchen',
          text:'Decor / Architecture',
          imgUrl: require('@/assets/img/project_3.png')
        },
        {
          name: 'Modern Kitchen',
          text:'Decor / Architecture',
          imgUrl: require('@/assets/img/project_4.png')
        }
      ],
      statisticsData: [
        {
          number: 12,
          title: 'Years Of Experience'
        },
        {
          number: 85,
          title: 'Success Project'
        },
        {
          number: 15,
          title: 'Active Project'
        },
        {
          number: 95,
          title: 'Happy Customers'
        }
      ],
      articlesAndNewsData: {
        isSubtitle: true,
        numberOfTitles: 3,
        titleAlign: 'center',
      }
    }
  },
  components: {
    FooterComponent,
    HeaderComponent,
    ArticlesAndNewsComponent, StatisticComponent, FollowProjectsComponent, GetStartedComponent}
}
</script>

<template>
  <HeaderComponent/>
  <GetStartedComponent :mainPageStartedURL="mainPageStartedURL"/>
  <FollowProjectsComponent :followProjects="followProjectsData"/>
  <StatisticComponent :statisticsData="statisticsData"/>
  <ArticlesAndNewsComponent :articlesAndNewsData="articlesAndNewsData"/>
  <FooterComponent/>
</template>

<style scoped lang="scss">

</style>