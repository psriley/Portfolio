<template>
  <div class="grid">
    <clickable-placeholder-image size="sm" :content="content[1]" />
    <clickable-placeholder-image size="sm" :content="content[2]" />
    <clickable-placeholder-image size="sm" :content="content[3]" />
    <clickable-placeholder-image size="sm" :content="content[4]" />
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
          title: "Unworthy",
          description:
              "This is the description for Unworthy!: Lorem ipsum dolor sit amet, consectetur adipisicing elit. " +
              "Debitis eos ex illum perspiciatis? Ab atque excepturi explicabo nam non placeat qui quidem " +
              "tempore totam voluptates.",
          gameLink: "https://sheepsully.itch.io/unworthy",
          devlogLink: "https://youtube.com/playlist?list=PLaHKVhWJHVGntz8lQW2Q-YAarNViwic1f&si=-tB4lBLJjlOCvcGH",
          tags: [
              "Unity",
              "PC",
              "Mac",
          ],
          // image: ,
        },
        2: {
          title: "Cat Burglar",
          description: "This is the description for Cat Burglar!",
          // image: ,
        },
        3: {
          title: "Let Your Light Shine",
          description: "This is the description for Let Your Light Shine!",
        },
        4: {
          title: "Sneak Out",
          description: "",
        }
      }
    }
  }
}
</script>