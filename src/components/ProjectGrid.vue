<template>
  <div class="grid">
    <clickable-placeholder-image size="sm" :content="content[1]" />
    <clickable-placeholder-image size="sm" :content="content[2]" />
<!--    <clickable-placeholder-image size="sm" />-->
<!--    <clickable-placeholder-image size="sm" />-->
<!--    <clickable-placeholder-image size="sm" />-->
<!--    <clickable-placeholder-image size="sm" />-->
<!--    <clickable-placeholder-image size="sm" />-->
<!--    <clickable-placeholder-image size="sm" />-->
<!--    <clickable-placeholder-image size="sm" />-->
<!--    <clickable-placeholder-image size="sm" />-->
  </div>
</template>

<script setup>
import ClickablePlaceholderImage from "@/components/ClickablePlaceholderImage.vue";
</script>

<script>
export default {
  name: 'ProjectGrid',
  data() {
    return {
      content: {
        1: {
          title: "Project 1",
          description: "This is the description for Project 1!",
          // image: ,
        },
        2: {
          title: "Project 2",
          description: "This is the description for Project 2!",
          // image: ,
        }
      }
    }
  }
}
</script>