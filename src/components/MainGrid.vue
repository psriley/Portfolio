<script setup>
import PlaceholderImage from "@/components/PlaceholderImage.vue";
</script>

<template>
  <div class="grid">
    <div>
      <PlaceholderImage image="/src/assets/unworthy_art2.png" subtitle="I make games"/>
      <!-- <PlaceholderImage text="Game Art Here" subtitle="I make games"/> -->
    </div>
    <div>
      <placeholder-image text="+" :show-image="false"/>
    </div>
    <div>
      <PlaceholderImage image="/src/assets/devlog_thumbnail.jpg" subtitle="and devlogs about those games"/>
      <!-- <PlaceholderImage text="YouTube Devlog Thumbnail Here" subtitle="and devlogs about those games"/> -->
    </div>
  </div>
</template>
