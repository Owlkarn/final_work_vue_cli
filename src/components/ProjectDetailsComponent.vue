<script>
import HeaderComponent from "@/components/UI/HeaderComponent.vue";
import FooterComponent from "@/components/UI/FooterComponent.vue";
import MainBlogComponent from "@/components/UI/MainBlogComponent.vue";
import {mapGetters} from "vuex";
import ProjectDetailsTextComponent from "@/components/UI/ProjectDetailsTextComponent.vue";
import CarouselComponent from "@/components/UI/CarouselComponent.vue";

export default {
  name: "ProjectDetailsComponent",
  components: {CarouselComponent, ProjectDetailsTextComponent, MainBlogComponent, FooterComponent, HeaderComponent},
  computed: {
    ...mapGetters(['getLargeMainImgs', 'getProjectDetailsText'])
  }
}
</script>

<template>
  <HeaderComponent/>
  <MainBlogComponent :mainImg="getLargeMainImgs[3]"/>
  <ProjectDetailsTextComponent :projectDetailsText="getProjectDetailsText[0]"/>
  <CarouselComponent/>
  <FooterComponent/>
</template>

<style scoped lang="scss">

</style>