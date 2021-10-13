<template>
  <div id="UNIQUE_COMPONENT_NAME">
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
  name: "UNIQUE_COMPONENT_NAME",
  freeConfig: freeConfig,
  data() {
    return {};
  },
  methods: {},
};
</script>

<style rel="stylesheet/scss" lang="scss">
#UNIQUE_COMPONENT_NAME {
}
</style>
