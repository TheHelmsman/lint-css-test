<template>
  <div class="hc-topmenu">
    <ul className="main-menu">
      <li v-for="item in list" :key="item.id">
        <a :href="item.link" class="hc-menu-link">{{ item.name }}</a>
      </li>
    </ul>
  </div>
</template>

<script lang="ts">
import { Vue } from 'vue-class-component';
export default class Topmenu extends Vue {
  data() {
    return {
      list: [
        {
          id: 1,
          name: 'Your work',
          link: '#',
        },
        {
          id: 2,
          name: 'Projects',
          link: '#',
        },
        {
          id: 3,
          name: 'Filters',
          link: '#',
        },
        {
          id: 4,
          name: 'Dashboards',
          link: '#',
        },
        {
          id: 5,
          name: 'People',
          link: '#',
        },
        {
          id: 6,
          name: 'Apps',
          link: '#',
        },
      ],
    };
  }
}
</script>

<style lang="scss" scoped>
.hc-topmenu {
  grid-area: menu;
}
.main-menu {
  display: flex;
  flex-direction: row;
}
li {
  margin-right: 10px;
}
.hc-menu-link {
  color: var(--blue_800);
  &:hover {
    color: var(--blue_300);
  }
}
</style>
