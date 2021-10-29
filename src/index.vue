<template>
  <div>
    <div
      :style="{
        color: freeStyle.fontColor,
      }"
      @click="funcName()"
    >
      {{ freeData.text }}
    </div>
  </div>
</template>

<script>
import freeConfig from "./free.config";
import needRely from "./needRely";
export default {
  name: "COMPONENT_NAME",
  components: {
    // ...按需引入组件
  },
  use: {
    // ...按需引入组件
  },
  needRely: needRely,
  freeConfig: freeConfig,
  data() {
    return {};
  },
  methods: {},
};
</script>

<style rel="stylesheet/scss" lang="scss" scope></style>
