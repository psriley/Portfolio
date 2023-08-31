<template>
  <ul>
    <li v-for="(section, index) in sections" :key="index" :class="{ active: activeSection === index }">
<!--        The bound href here works because we have bound the id to our h2 elements above-->
      <a :href="'#' + section.id">{{ section.title }}</a>
    </li>
  </ul>
</template>

<script setup>
// import { ref, onMounted } from 'vue';
// const currentSection = ref('')

// onMounted(() => {
//     const observer = new IntersectionObserver((entries) => {
//       console.log(entries);
//       entries.forEach((entry) => {
//         console.log(entry);
//         if (entry.intersectionRatio > 0) {
//           this.currentSection.value = entry.target.getAttribute('id')
//         }
//       })
//       document.querySelectorAll('h2').forEach((section) => {
//         observer.observe(section);
//       })
//     })
//   })
</script>

<script>
export default {
  name: 'MenuBar',
  data() {
    return {
      // headers: [
      //     'ABOUT',
      //     'PROJECTS',
      //     'GAME JAM GAMES',
      //     'WORK EXPERIENCE',
      // ],
      sections: [
        { id: 'projects', title: 'Projects', offsetTop: 0 },
        { id: 'section-2', title: 'Section 2', offsetTop: 0 },
        // Add more sections here
      ],
      activeSection: null,
    }
  },
  methods: {
    // scrollToSection(index) {
    //   const offset = this.sections[index].offsetTop;
    //   window.scrollTo({ top: offset, behavior: 'smooth' });
    // },
    // updateActiveSection() {
    //   const scrollPosition = window.scrollY;
    //
    //   for (let i = 0; i < this.sections.length; i++) {
    //     if (
    //       scrollPosition >= this.sections[i].offsetTop &&
    //       (i === this.sections.length - 1 || scrollPosition < this.sections[i + 1].offsetTop)
    //     ) {
    //       this.activeSection = i;
    //       break;
    //     }
    //   }
    // },
  },
  // mounted() {
  //   // Calculate the offsetTop for each section
  //   this.sections.forEach((section, index) => {
  //     section.offsetTop = document.querySelector(`#section-${index}`).offsetTop;
  //   });
  //
  //   // Add a scroll event listener to update active section
  //   window.addEventListener('scroll', this.updateActiveSection);
  // },
  // beforeUnmount() {
  //   // Remove the scroll event listener when the component is destroyed
  //   window.removeEventListener('scroll', this.updateActiveSection);
  // },
}
</script>
