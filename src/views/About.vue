<template>
  <div class="hc-about">
    <h1>Introduction to tables</h1>
    <p>
      The HTML table model allows authors to arrange data -- text, preformatted text, images, links, forms, form fields, other tables, etc.
      -- into rows and columns of cells. Each table may have an associated caption (see the CAPTION element) that provides a short
      description of the table's purpose. A longer description may also be provided (via the summary attribute) for the benefit of people
      using speech or Braille-based user agents.
      <br />
      <br />
      Table rows may be grouped into a head, foot, and body sections, (via the THEAD, TFOOT and TBODY elements, respectively). Row groups
      convey additional structural information and may be rendered by user agents in ways that emphasize this structure. User agents may
      exploit the head/body/foot division to support scrolling of body sections independently of the head and foot sections. When long
      tables are printed, the head and foot information may be repeated on each page that contains table data. Authors may also group
      columns to provide additional structural information that may be exploited by user agents.
      <br />
      <br />
      Furthermore, authors may declare column properties at the start of a table definition (via the COLGROUP and COL elements) in a way
      that enables user agents to render the table incrementally rather than having to wait for all the table data to arrive before
      rendering.
      <br />
      <br />
      Table cells may either contain "header" information (see the TH element) or "data" (see the TD element). Cells may span multiple rows
      and columns. The HTML 4 table model allows authors to label each cell so that non-visual user agents may more easily communicate
      heading information about the cell to the user. Not only do these mechanisms greatly assist users with visual disabilities, they make
      it possible for multi-modal wireless browsers with limited display capabilities (e.g., Web-enabled pagers and phones) to handle
      tables.
      <br />
      <br />
      Tables should not be used purely as a means to layout document content as this may present problems when rendering to non-visual
      media. Additionally, when used with graphics, these tables may force users to scroll horizontally to view a table designed on a system
      with a larger display. To minimize these problems, authors should use style sheets to control layout rather than tables.
    </p>
  </div>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';
import { getModule } from 'vuex-module-decorators';

import ModuleA from '@/store/moduleA';
import ModuleB from '@/store/moduleB';

import { Button } from '@/components/Button';

@Options({
  components: {
    Button,
  },
})
export default class About extends Vue {
  // ---

  get count(): number {
    return ModuleA.getCount;
  }

  // ---
  created(): void {
    //
  }

  mounted(): void {
    ModuleA.increment(1);

    // console.log(this.);
  }
}
</script>
<style lang="scss" scoped>
@import '/src/styles/index.scss';
.hc-about {
}
h1 {
  @include hc-general-title;
}
</style>
