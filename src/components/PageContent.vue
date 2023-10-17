<template>
  <div class="sections">
    <my-projects/>
<!--    <section v-for="(header, index) in headers" :key="index">-->
<!--      <h2 ref="header">{{ header }}</h2>-->
<!--      <p>Here is some information about {{ header }}. Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do-->
<!--        eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation-->
<!--        ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate-->
<!--        velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa-->
<!--        qui officia deserunt mollit anim id est laborum.</p>-->
<!--    </section>-->
  </div>
</template>

<script>
import MyProjects from "@/components/MyProjects.vue";

export default {
  name: 'PageContent',
  components: {MyProjects},
  data() {
    return {
      // headers: [
      //     'ABOUT',
      //     'PROJECTS',
      //     'GAME JAM GAMES',
      //     'WORK EXPERIENCE',
      // ]
    }
  },
}
</script>
