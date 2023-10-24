<!--<template>-->
<!--  <div @click="showModal = true">-->
<!--    <div class="placeholder-sm">-->
<!--      <p>{{ text }}</p>-->
<!--    </div>-->
<!--  </div>-->
<!--  <div class="modal-bg" v-if="showModal">-->
<!--    <div class="modal" ref="modal">-->
<!--      <button @click="showModal = false" class="close-btn">x</button>-->
<!--      Click outside this modal to close it-->
<!--    </div>-->
<!--  </div>-->
<!--&lt;!&ndash;  <transition name="fade">&ndash;&gt;-->
<!--&lt;!&ndash;    <div class="modal-bg" v-if="showModal" @click="showModal = false"></div>&ndash;&gt;-->
<!--&lt;!&ndash;  </transition>&ndash;&gt;-->
<!--&lt;!&ndash;  <transition name="slide">&ndash;&gt;-->
<!--&lt;!&ndash;    <div class="modal">&ndash;&gt;-->
<!--&lt;!&ndash;      <h1>Lorem Ipsum</h1>&ndash;&gt;-->
<!--&lt;!&ndash;      <p>&ndash;&gt;-->
<!--&lt;!&ndash;        Lorem ipsum dolor sit amet, consectetur adipisicing elit. Commodi cum delectus eum minus necessitatibus&ndash;&gt;-->
<!--&lt;!&ndash;        perferendis placeat provident sed voluptas voluptatem.&ndash;&gt;-->
<!--&lt;!&ndash;      </p>&ndash;&gt;-->
<!--&lt;!&ndash;      <button class="button" @click="showModal = false">Close Modal</button>&ndash;&gt;-->
<!--&lt;!&ndash;    </div>&ndash;&gt;-->
<!--&lt;!&ndash;  </transition>&ndash;&gt;-->
<!--&lt;!&ndash;  <div class="modal-bg" v-if="isModalOpen">&ndash;&gt;-->
<!--&lt;!&ndash;    <div class="modal" ref="modal">&ndash;&gt;-->
<!--&lt;!&ndash;      <button @click="isModalOpen = false" class="close-btn">x</button>&ndash;&gt;-->
<!--&lt;!&ndash;      Click outside this modal to close it&ndash;&gt;-->
<!--&lt;!&ndash;    </div>&ndash;&gt;-->
<!--&lt;!&ndash;  </div>&ndash;&gt;-->
<!--</template>-->

<!--<script>-->
<!--export default {-->
<!--  name: 'ClickablePlaceholderImage',-->
<!--  data() {-->
<!--    return {-->
<!--      showModal: true-->
<!--    }-->
<!--  },-->
<!--  props: {-->
<!--    text: {-->
<!--      type: String,-->
<!--      required: false,-->
<!--      default: "Placeholder",-->
<!--    },-->
<!--  }-->
<!--}-->
<!--</script>-->


<template>
  <div>
    <div class="placeholder-sm" @click="openModal">
      <p>{{ text }}</p>
    </div>
<!--    <button @click="openModal">Open Modal</button>-->
    <transition name="modal-animation">
      <div v-if="isModalOpen" class="modal" @click="closeModal">
        <div class="modal-content" @click.stop>
          <modal-content
              :title="content['title']"
              :description="content['description']"
              :game-link="content['gameLink']"
              :devlog-link="content['devlogLink']"
              :tags="content['tags']"
          />
          <div class="close" @click="closeModal">&times;</div>
        </div>
      </div>
    </transition>
  </div>
</template>

<script>
import ModalContent from "@/components/ModalContent.vue";

export default {
  name: 'ClickablePlaceholderImage',
  components: {ModalContent},
  data() {
    return {
      isModalOpen: false,
    };
  },
  props: {
    text: {
      type: String,
      required: false,
      default: "Placeholder",
    },
    content: {
      type: Object,
      required: true,
    }
  },
  methods: {
    openModal() {
      this.isModalOpen = true;
    },
    closeModal() {
      this.isModalOpen = false;
    },
  },
};
</script>
