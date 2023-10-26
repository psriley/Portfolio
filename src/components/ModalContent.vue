<template>
  <label>{{ title }}</label>
  <div>
    <span v-for="tag in tags" :key="tag" :class="tag" style="margin: 10px">
      <button>{{ tag }}</button>
    </span>
  </div>
  <div class="grid">
    <!-- gif of gameplay -->
    <!-- link to page -->
    <!-- platforms -->
    <!-- description -->
    <!-- tools (unity) -->
    <!-- devlog series (if applicable) -->
    <!-- things learned -->
    <div>
      <div style="margin: 5vh auto; border: 2px dashed black" class="placeholder-sm" />
    </div>
    <div>
      <div style="margin-bottom: 5vh;">
        <p>{{ description }}</p>
        <p>Made with: Unity</p>
        <p>Platforms: PC, Mac</p>
      </div>
      <div>
        <a v-if="gameLink" :href="gameLink" class="modal-link">Itch.io Page</a>
        <a v-if="devlogLink" :href="devlogLink" class="modal-link">Devlog Series</a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ModalContent',
  props: {
    title: {
      type: String,
      required: true,
    },
    description: {
      type: String,
      required: true,
    },
    gameLink: {
      type: String,
      required: false,
    },
    devlogLink: {
      type: String,
      required: false,
    },
    tags: {
      type: Array,
      required: false,
    },
    fileName: {
      type: String,
      required: false,
      default: ".../src/assets/placeholderImage",
    }
  }
}
</script>