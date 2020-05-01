<template>
  <div>
    <h2>分类</h2>
    <scroll @scroll="contentScroll"></scroll>
    <back-top @click.native="backClick" v-show="isShowBackTop" />
  </div>
</template>

<script>
import Scroll from "components/common/scroll/Scroll";
import { backTopMixin } from "common/mixin";

export default {
  name: "Category",
  mixins: [backTopMixin],
  components: {
    Scroll
  },
  methods: {
    contentScroll(position) {
      this.isShowBackTop = -position.y > 1000;
    }
  }
};
</script>

<style scoped>
</style>
