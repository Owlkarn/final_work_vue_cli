<template>
  <ProjectPageComponent/>
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
import '@/assets/fonts/stylesheet.css'
import ProjectPageComponent from "@/components/ProjectPageComponent.vue";
// import StartPageComponent from "@/components/StartPageComponent.vue";
</script>