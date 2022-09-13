<template>
  <div class="hc-sidebar">
    <div class="title">Sidebar</div>
    <ul>
      <li><a href="/" class="hc-sidebar-link">Home link</a></li>
      <li><a href="/about" class="hc-sidebar-link">About link</a></li>
    </ul>
  </div>
</template>

<script lang="ts">
import { Vue } from 'vue-class-component';
export default class Sidebar extends Vue {}
</script>

<style lang="scss" scoped>
@import '/src/styles/index.scss';
.hc-sidebar {
  grid-area: sidebar;
  @include hc-general-padding;
}
.hc-sidebar-link {
  color: var(--social_line_800);
  &:hover {
    color: var(--social_line_500);
  }
}
</style>
