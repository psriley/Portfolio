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
          <span class="close" @click="closeModal">&times;</span>
          <p>Modal content goes here.</p>
        </div>
      </div>
    </transition>
  </div>
</template>

<script>
export default {
  name: 'ClickablePlaceholderImage',
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

<style>
.modal {
  /* always fix our modal to the viewport */
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;

  /* darken the screen behind the modal */
  background-color: rgba(0, 0, 0, 0.5);

  /* center the modal */
  display: flex;
  justify-content: center;
  align-items: center;
}

.modal-content {
  /* needed to position the button */
  position: relative;

  background: white;
  padding: 50px 100px;
  border-radius: 5px;
  box-shadow: 0px 10px 5px 2px rgba(0, 0, 0, 0.1);
}

.close {
  cursor: pointer;
  color: red;
}

.modal-animation-enter-active,
.modal-animation-leave-active {
  transition: opacity .3s cubic-bezier(.52, .02, .19, 1.02);
}

.modal-animation-enter-from,
.modal-animation-leave-to {
  opacity: 0;
}

.modal-animation-enter-to,
.modal-animation-leave-from {
  opacity: 1;
}
</style>
