<template>
<footer class="row">
  <div class="col-sm-6">
    <div id="footer_segment1_mount">
      loading...
    </div>
  </div>
  <div class="col-sm-3">
    <div id="footer_segment2_mount">
      loading...
    </div>
  </div>
  <div class="col-sm-3">
    <div id="footer_segment3_mount">
      loading...
    </div>
  </div>
</footer>
</template>
<script>
import {inject} from "../js/componentinjector.js";
export default {
  data () {
    return {

    }
  },
  mounted: function () {
    console.log("BlankFooter2.vue mounted");
    this.mountSegment1();
  },
  methods: {
    mountSegment1: function() {
      const FooterSegment1 = resolve => {
        require.ensure(['./FooterSegment1.vue'], () => {
          resolve(require('./FooterSegment1.vue'))
        })
      };
      inject("#footer_segment1_mount", FooterSegment1);
      this.mountSegment2();
    },
    mountSegment2: function() {
      const FooterSegment2 = resolve => {
        require.ensure(['./FooterSegment2.vue'], () => {
          resolve(require('./FooterSegment2.vue'))
        })
      };
      inject("#footer_segment2_mount", FooterSegment2);
      this.mountSegment3();
    },
    mountSegment3: function() {
      const FooterSegment3 = resolve => {
        require.ensure(['./FooterSegment3.vue'], () => {
          resolve(require('./FooterSegment3.vue'))
        })
      };
      inject("#footer_segment3_mount", FooterSegment3);
    }
  }
}
</script>