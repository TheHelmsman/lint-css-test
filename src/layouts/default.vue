<template>
  <div class="x-layout">
    <Header data-aos="fade-down" data-aos-duration="500">Header</Header>
    <Sidebar />
    <div className="page-content">
      <transition mode="out-in" name="fade">
        <router-view />
      </transition>
    </div>
    <Footer data-aos="fade-up" data-aos-duration="500">Footer</Footer>
  </div>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';
import Header from '@/components/header/Header.vue';
import Footer from '@/components/footer/Footer.vue';
import Sidebar from '@/components/sidebar/Sidebar.vue';

@Options({
  name: 'DefaultLayout',
  components: { Header, Footer, Sidebar },
})
export default class extends Vue {}
</script>

<style lang="scss" scoped>
.x-layout {
  width: 100%;
  height: 100vh;
  display: grid;
  grid-template-columns: 3fr 3fr 3fr 3fr;
  grid-template-rows: 1fr 10fr 1fr;
  grid-template-areas:
    'header header header header'
    'sidebar main main main'
    'footer footer footer footer';
}
.page-content {
  grid-area: main;
}
</style>
