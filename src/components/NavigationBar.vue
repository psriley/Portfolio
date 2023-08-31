<template>
  <div class="nav">
    <ul>
      <li @mouseenter="swapIcon" @mouseleave="swapIcon"><a href="https://github.com/IrishGingy" target="_blank">
        <img alt="link to github account" :src="navigation_sprites.github['icon']"/></a>
      </li>
      <li @mouseenter="swapIcon" @mouseleave="swapIcon"><a href="https://sheepsully.itch.io/" target="_blank">
        <img alt="link to itch.io account" :src="navigation_sprites.itchio['icon']"/></a>
      </li>
      <li @mouseenter="swapIcon" @mouseleave="swapIcon"><a href="https://www.youtube.com/@SheepSully" target="_blank">
        <img alt="link to youtube channel" :src="navigation_sprites.youtube['icon']"/></a>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'NavigationBar',
  data() {
    return {
      navigation_sprites: {
          github: {
            icon: '',
            enterIcon: 'src/assets/github/github-mark.svg',
            exitIcon: 'src/assets/github/github-mark-white.svg',
          },
          itchio: {
            icon: '',
            enterIcon: 'src/assets/itchio/itchio-logo-textless-black.svg',
            exitIcon: 'src/assets/itchio/itchio-logo-textless-white.svg',
          },
          youtube: {
            icon: '',
            enterIcon: 'src/assets/youtube/youtube_social_squircle_dark.png',
            exitIcon: 'src/assets/youtube/youtube_social_squircle_white.png',
          }
      }
    };
  },
  created () {
      this.initializeIcons();
  },
  methods: {
      swapIcon(event) {
        const elementContent = event.srcElement.innerHTML;

        for (const key in this.navigation_sprites) {
          if (Object.prototype.hasOwnProperty.call(this.navigation_sprites, key)) {
            const item = this.navigation_sprites[key];
            if (elementContent.includes(key)){
              item.icon = event.type === 'mouseenter' ? item.enterIcon : item.exitIcon;
            }
          }
        }
      },
      initializeIcons() {
        for (const key in this.navigation_sprites) {
          if (Object.prototype.hasOwnProperty.call(this.navigation_sprites, key)) {
            const item = this.navigation_sprites[key];
            if (item && item.exitIcon !== undefined) {
              item.icon = item.exitIcon;
            }
          }
        }
      },
  },
}
</script>
