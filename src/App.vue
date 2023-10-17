<template>
  <header>
    <div>
      <navigation-bar/>
    </div>
    PEYTON RILEY
  </header>
  <body>
    <aside class="menu">
      <menu-bar/>
    </aside>
    <div class="content">
      <div class="main">
        <main-grid/>
        <div>
          <page-content/>
        </div>
      </div>
<!--      <div>-->
<!--        <page-content/>-->
<!--      </div>-->
    </div>
  </body>
<!--  <button @click="isModalOpen = true">Open Modal</button>-->
<!--  <div class="modal-bg" v-if="isModalOpen">-->
<!--    <div class="modal" ref="modal">-->
<!--      <button @click="isModalOpen = false" class="close-btn">x</button>-->
<!--      Click outside this modal to close it-->
<!--    </div>-->
<!--  </div>-->

<!--  <Teleport to="#modal">-->
<!--    <Transition name="modal">-->
<!--      <div class="modal-bg" v-if="isModalOpen">-->
<!--        <div class="modal" ref="modal">-->
<!--          <button @click="isModalOpen = false" class="close-btn">x</button>-->
<!--          Click outside this modal to close it-->
<!--        </div>-->
<!--      </div>-->
<!--    </Transition>-->
<!--  </Teleport>-->
</template>

<script>
import { ref } from 'vue';
import MainGrid from "@/components/MainGrid.vue";
import NavigationBar from "@/components/NavigationBar.vue";
import MenuBar from "@/components/MenuBar.vue";
import PageContent from "@/components/PageContent.vue";

const isModalOpen = ref(false);

export default {
  name: 'App',
  components: {MainGrid, NavigationBar, MenuBar, PageContent},
  data() {
    return {
      isModalOpen
    }
  },
  // methods: {
  //   modalClick() {
  //     console.log("clicked modal");
  //   },
  //   onClick() {
  //     console.log("yup, clicked");
  //   },
  //   showModal() {
  //     console.log("show modal");
  //   }
  // },
  // mounted() {
  //   this.ref.addEventListener('click', this.modalClick);
  //   document.addEventListener('click', this.onClick);
  // },
  // beforeUnmount() {
  //   this.ref.removeEventListener('click', this.modalClick);
  //   document.removeEventListener('click', this.onClick);
  // },
}
</script>
