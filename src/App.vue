<script setup>
import MainGrid from "@/components/MainGrid.vue";
import NavigationBar from "@/components/NavigationBar.vue";
import MenuBar from "@/components/MenuBar.vue";
import PageContent from "@/components/PageContent.vue";
</script>

<template>
  <div>
    <navigation-bar/>
  </div>
  <header>
    PEYTON RILEY
    <div class="menu">
      <menu-bar/>
    </div>
  </header>
  <div class="main">
    <main-grid/>
  </div>
  <div>
    <page-content/>
  </div>
</template>
