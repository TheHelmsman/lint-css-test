<template>
  <div class="hc-footer">Footer</div>
</template>

<script lang="ts">
import { Vue } from 'vue-class-component';
export default class Footer extends Vue {}
</script>

<style lang="scss" scoped>
@import '/src/styles/index.scss';
.hc-footer {
  grid-area: footer;
  @include hc-general-padding;
}
</style>
