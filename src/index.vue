<template>
  <div id="COMPONENT_NAME">
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
export default {
  name: "COMPONENT_VERSION",
  components:{
    // ...按需引入组件
  },
  use:{
    // ...按需引入组件
  },
  freeConfig: freeConfig,
  data() {
    return {};
  },
  methods: {},
};
</script>

<style rel="stylesheet/scss" lang="scss" scope>
</style>
