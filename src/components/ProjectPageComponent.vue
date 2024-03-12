<script>
import HeaderComponent from "@/components/UI/HeaderComponent.vue";
import MainBlogComponent from "@/components/UI/MainBlogComponent.vue";
import FooterComponent from "@/components/UI/FooterComponent.vue";
import ProjectCategoriesComponent from "@/components/UI/ProjectCategoriesComponent.vue";
import ProjectsInTwoColumnsComponent from "@/components/UI/ProjectsInTwoColumnsComponent.vue";
import PageButtons from "@/components/UI/PageButtons.vue";

export default {
  name: "ProjectPageComponent",
  components: {
    PageButtons,
    ProjectsInTwoColumnsComponent,
    ProjectCategoriesComponent, FooterComponent, MainBlogComponent, HeaderComponent},
  data() {
    return {
      mainImg: {
        imgUrl: require('@/assets/img/projects_main.png'),
        isTitle: true,
        title: 'Our Project',
        subtitle: 'Home / Project',
      },
      categories: ['Bathroom', 'Bedroom', 'Kitchen', 'Living Area'],
      projectsData: [
        {
          name: 'Minimal Bedroom',
          text:'Decor / Architecture',
          imgUrl: require('@/assets/img/project_img_1.png'),
          isFavourite: true,
          tags: ['Bathroom', 'Bedroom']
        },
        {
          name: 'Minimal Bedroom',
          text:'Decor / Architecture',
          imgUrl: require('@/assets/img/project_img_2.png'),
          isFavourite: false,
          tags: ['Bedroom', 'Kitchen']
        },
        {
          name: 'Modern Bedroom',
          text:'Decor / Architecture',
          imgUrl: require('@/assets/img/project_img_3.png'),
          isFavourite: false,
          tags: ['Kitchen', 'Living Area']
        },
        {
          name: 'Classic Minimal Bedroom',
          text:'Decor / Architecture',
          imgUrl: require('@/assets/img/project_img_4.png'),
          isFavourite: true,
          tags: ['Bathroom', 'Living Area']
        },
        {
          name: 'Minimal Bedroom table',
          text:'Decor / Architecture',
          imgUrl: require('@/assets/img/project_img_5.png'),
          isFavourite: false,
          tags: ['Bathroom', 'Kitchen']
        },
        {
          name: 'System Table',
          text:'Decor / Architecture',
          imgUrl: require('@/assets/img/project_img_6.png'),
          isFavourite: false,
          tags: ['Bedroom', 'Living Area']
        },
        {
          name: 'Modern Bedroom',
          text:'Decor / Architecture',
          imgUrl: require('@/assets/img/project_img_7.png'),
          isFavourite: false,
          tags: ['Bathroom', 'Bedroom']
        },
        {
          name: 'Modern Bedroom',
          text:'Decor / Architecture',
          imgUrl: require('@/assets/img/project_img_8.png'),
          isFavourite: false,
          tags: ['Kitchen', 'Living Area']
        },
      ],
    }
  },
  methods: {
    filterProjects(event, tag) {
      const projectEls = document.querySelectorAll('.projectsInTwoColumns__project');
      if (event.currentTarget.classList.contains("project-categories__block_category-active")) {
        event.currentTarget.classList.remove("project-categories__block_category-active");
        projectEls.forEach(el => {
          el.style.display = 'block';
        })
      } else {
        const tagEls = document.querySelectorAll('.project-categories__block_category-active');
        if (tagEls.length > 0) {
          tagEls.forEach(el => {
            el.classList.remove('project-categories__block_category-active');
          })
        }
        event.currentTarget.classList.add("project-categories__block_category-active");
        const filteredProjects = this.projectsData.filter(project => project.tags.includes(tag));
        const indexesOfFilteredProjects = filteredProjects.map(project => this.projectsData.indexOf(project));
        projectEls.forEach((el, index) => {
          el.style.display = 'none';
          if (indexesOfFilteredProjects.includes(index)) {
            el.style.display = 'block';
          }
        })
      }
    }
  }
}
</script>

<template>
  <HeaderComponent/>
  <MainBlogComponent :mainImg="mainImg"/>
  <ProjectCategoriesComponent :categories="categories" :filterFunction="filterProjects"/>
  <ProjectsInTwoColumnsComponent :projectsData="projectsData"/>
  <PageButtons/>
  <FooterComponent/>
</template>

<style scoped lang="scss">

</style>