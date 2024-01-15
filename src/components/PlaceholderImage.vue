<template>
  <div>
    <div :class="placeholderClass">
      <img v-if="image" class="fit-image" :src="image"/>
      <p v-else>{{ text }}</p>
      <p class="subtitle">
        <i>{{ subtitle }}</i>
      </p>
    </div>
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
    },
    subtitle: {
      type: String,
      required: false,
    },
    showImage: {
      type: Boolean,
      required: false,
      default: true,
    },
    size: {
      type: String,
      required: false,
      default: "lg",
    },
    image: {
      type: String,
      required: false,
    },
  },
  computed: {
    placeholderClass() {
      let classes = "";
      classes += this.showImage ? "placeholder" : "placeholder-no-show";
      if (this.size === "sm" && this.showImage) {
        classes += " placeholder-sm";
      } else if (this.size === "sm" && !this.showImage) {
        classes += " placeholder-no-show";
      }
      // classes += this.size === "sm" ? " placeholder-sm" : if this.showImage " placeholder";
      return classes;
    }
  }
}
</script>
