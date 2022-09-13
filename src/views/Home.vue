<template>
  <div class="hc-home">
    <h1 class="--spacer">Example of content formatting</h1>
    <Button class="--spacer">Test 123</Button>
    <table class="hc-table">
      <thead>
        <tr>
          <th class="hc-th hc-cell --bold" rowspan="2">Gender</th>
          <th class="hc-th hc-cell --bold" colspan="2">Average</th>
          <th class="hc-th hc-cell --bold" rowspan="2">Red eyes</th>
        </tr>
        <tr>
          <th class="hc-th hc-cell">height</th>
          <th class="hc-th hc-cell">weight</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td class="hc-td --cell-primary hc-cell --bold">Males</td>
          <td class="hc-td --cell-male hc-cell">1.9</td>
          <td class="hc-td --cell-male hc-cell">0.003</td>
          <td class="hc-td --cell-male hc-cell">40%</td>
        </tr>
        <tr>
          <td class="hc-td --cell-secondary hc-cell --bold">Females</td>
          <td class="hc-td --cell-female hc-cell">1.7</td>
          <td class="hc-td --cell-female hc-cell">0.002</td>
          <td class="hc-td --cell-female hc-cell">43%</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';

import { Button } from '@/components/Button';

@Options({
  components: {
    Button,
  },
})
export default class Home extends Vue {}
</script>

<style lang="scss" scoped>
@import '/src/styles/index.scss';
.hc-home {
}
.hc-table,
.hc-th,
.hc-td {
  border: 1px solid var(--white_alpha_40);
  @include hc-general-padding;
}
.hc-cell {
  color: var(--white);
}
.--bold {
  font-weight: bold;
}
.--cell-primary {
  color: var(--social_vk_800);
}
.--cell-secondary {
  color: var(--pink_800);
}
.--cell-male {
  color: var(--social_twitter_500);
}
.--cell-female {
  color: var(--pink_300);
}
.--spacer {
  margin-bottom: 25px;
}
h1 {
  @include hc-general-title;
}
</style>
