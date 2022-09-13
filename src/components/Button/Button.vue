<template>
  <a :class="classes" @click="onClick">
    <slot />
  </a>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';

import log from '@/log';

@Options({
  props: {
    type: {
      type: String,
      default: 'primary',
    },
    size: {
      type: String,
      default: 'sm',
    },
  },
  name: 'Button',
})
export default class Button extends Vue {
  public active = false;

  // --- props

  public type!: '' | 'primary' | 'success' | 'warning' | 'danger' | 'info' | 'text';
  public size!: '' | 'xs' | 'sm' | 'md' | 'lg' | 'xl';

  // --- computed

  get class(): string {
    return `x-${this.$options.name?.toLowerCase()}`;
  }

  get classSize(): string {
    return this.size ? ['-', this.size].filter(Boolean).join('-') : '';
  }

  get classType(): string {
    return this.type ? ['-', this.type].filter(Boolean).join('-') : '';
  }

  get classActive(): string {
    return this.active ? '--active' : '';
  }

  get classes(): string[] {
    return [...new Set<string>([this.class, this.classSize, this.classType, this.classActive])];
  }

  // --- hooks

  public beforeCreate?(): void {
    this.$log(`beforeCreate`);
  }

  public created?(): void {
    this.$log(`created`);
  }

  public async serverPrefetch(): Promise<unknown> {
    this.$log(`serverPrefetch`);

    return null;
  }

  public beforeMount(): void {
    this.$log(`beforeMount`);
  }

  public mounted(): void {
    this.$log(`mounted`);
  }

  public beforeUpdate(): void {
    this.$log(`beforeUpdate`);
  }

  public updated(): void {
    this.$log(`updated`);
  }

  public beforeUnmount(): void {
    this.$log(`beforeUnmount`);
  }

  public unmounted(): void {
    this.$log(`unmounted`);
  }

  public activated(): void {
    this.$log(`activated`);
  }

  public deactivated(): void {
    this.$log(`deactivated`);
  }

  public errorCaptured?(err: Error, vm: Vue, info: string): boolean | undefined {
    log.error(`errorCaptured`, { err, vm, info });

    return true;
  }

  public onClick(): void {
    this.active = !this.active;
  }
}
</script>

<style scoped lang="scss">
@import '/src/styles/index.scss';
.x-button {
  display: inline-flex;
  align-items: center;
  background-color: var(--brand_secondary_800);
  cursor: pointer;
  border-radius: 3px;
  @include hc-general-padding;
  &:hover {
    background-color: var(--brand_secondary_500);
  }
  &.--active {
    background-color: var(--green_800);
  }
  &.--active:hover {
    background-color: var(--green_300);
  }
}
</style>
