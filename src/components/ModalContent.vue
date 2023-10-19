<template>
  <div>
    <label>{{ title }}</label>
    <p>{{ description }}</p>
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
    fileName: {
      type: String,
      required: false,
      default: ".../src/assets/placeholderImage",
    }
  }
}
</script>