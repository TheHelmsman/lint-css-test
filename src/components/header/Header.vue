<template>
  <div class="hc-header">
    <div className="top-bar">
      <Logo />
      <Topmenu />
      <Create />
    </div>
  </div>
</template>

<script lang="ts">
import { Vue, Options } from 'vue-class-component';
import Topmenu from './Topmenu.vue';
import Logo from './Logo.vue';
import Create from './Create.vue';

@Options({
  name: 'DefaultLayout',
  components: { Topmenu, Logo, Create },
})
export default class Header extends Vue {}
</script>

<style lang="scss" scoped>
@import '/src/styles/index.scss';
.hc-header {
  grid-area: header;
  @include hc-general-padding;
}
.top-bar {
  display: grid;
  grid-template-columns: 1fr 6fr 6fr;
  grid-template-rows: auto;
  grid-template-areas: 'logo menu create';
}
</style>
