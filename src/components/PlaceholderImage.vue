<template>
  <div class="placeholder">
    <p>{{ text }}</p>
  </div>
</template>

<script>
export default {
  name: 'PlaceholderImage',
  props: {
    text: {
      type: String,
      required: false,
      default: "Placeholder",
    }
  },
}
</script>
