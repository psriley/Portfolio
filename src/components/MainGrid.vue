<script setup>
import PlaceholderImage from "@/components/PlaceholderImage.vue";
</script>

<template>
  <div class="grid">
    <div>
      <PlaceholderImage text="Game Art Here" subtitle="I make games"/>
    </div>
    <div>
      <placeholder-image text="+" :show-image="false"/>
    </div>
    <div>
      <PlaceholderImage text="YouTube Devlog Thumbnail Here" subtitle="and devlogs about those games"/>
    </div>
  </div>
</template>
