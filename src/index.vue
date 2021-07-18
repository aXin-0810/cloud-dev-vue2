<template>
  <div id="UNIQUE_COMPONENT_NAME" :style="freeStyle">
    {{freeData.value}}
  </div>
</template>

<script>
export default {
  name: "UNIQUE_COMPONENT_NAME",
  props: {
    typography: {
      type:Object,
      default:()=>{
        return {
          width: "120px",
          height: "120px",
        }
      }
    },
    freeStyle: {
      type: Object,
      default: () => {
        return {
          fontSize: '12px',
        };
      },
    },
    freeData: {
      type: Object,
      default: () => {
        return {
          value:"value"
        };
      },
    },
    freeConfig: {
      type: Object,
      default: () => {
        return {
          animation:""
        };
      },
    },
  },
  data() {
    return {
      
    };
  },
  methods: {
    
  },
};
</script>

<style rel="stylesheet/scss" lang="scss">
#UNIQUE_COMPONENT_NAME{

}
</style>
