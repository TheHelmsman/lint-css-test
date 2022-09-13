<template>
  <div class="hc-create">
    <button className="create-button">Create</button>
    more top bar items here like search bar and profile menu
  </div>
</template>

<script lang="ts">
import { Vue } from 'vue-class-component';
export default class Create extends Vue {}
</script>

<style lang="scss" scoped>
.hc-create {
  grid-area: create;
  justify-self: end;
}
</style>
