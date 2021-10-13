<template>
  <div id="$name">
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
  name: "$name_version",
  freeConfig: freeConfig,
  data() {
    return {};
  },
  methods: {},
};
</script>

<style rel="stylesheet/scss" lang="scss" scope>
</style>
