<template>
  <div
    ref="editable"
    @click="clickev"
    @input="onInput"
    :contenteditable="controlPanel ? true : false"
    :style="{
      width: freeStyle._width,
      height: freeStyle._height,
      'pointer-events': 'auto',
    }"
  >
    {{ freeData.text }}
  </div>
</template>

<script>
export default {
  name: 'COMPONENT_NAME',
  props: {
    // 面板控制实例
    controlPanel: [Object, Function],
  },
  freeConfig: {
    /**
     * 根标签布局初始值（后面可以根据页面交互操作修改）
     * 属性支持:
     *  width             宽度
     *  height            高度
     *  top               上边距
     *  left              下边距
     *  transform.rotate  旋转角度
     */
    rootNodeStyle: {
      top: '0px',
      left: '0px',
      width: '200px',
      height: '60px',
      transform: { rotate: 0 },
    },
    /**
     * 自由样式
     * 属性:  自定义key
     */
    freeStyle: {
      _width: {
        label: '宽',
        _default: '100%',
      },
      _height: {
        label: '高',
        _default: '100%',
      },
    },
    /**
     * 自由数据
     * 属性:  自定义key
     */
    freeData: {
      text: {
        label: '文本内容',
        _default: '请输入你要的内容',
      },
    },
    /**
     * 自由绑定函数
     * 属性:  自定义函数名
     */
    freeBindMethods: {
      clickev: {
        label: '文本点击事件',
        _default(a) {
          console.log(a);
        },
      },
    },
  },
  mounted() {
    console.log(this?.controlPanel);
  },
  methods: {
    onInput(e) {
      if (this?.controlPanel?.setData) {
        const el = this.$refs.editable;
        // 保存当前光标位置
        const selection = window.getSelection();
        const range = selection.getRangeAt(0);
        const startOffset = range.startOffset;
        const startContainer = range.startContainer;
        // 更新内容
        this?.controlPanel?.setData('text', el.innerText, true);
        this.$nextTick(() => {
          // 恢复光标
          const newRange = document.createRange();
          // 有些复杂，需判断startContainer是否还有效，这里简化恢复到startOffset位置
          if (el.firstChild) {
            newRange.setStart(
              el.firstChild,
              Math.min(startOffset, el.firstChild.length)
            );
            newRange.collapse(true);
            selection.removeAllRanges();
            selection.addRange(newRange);
          }
        });
      }
    },
  },
};
</script>

<style rel="stylesheet/scss" lang="scss" scope></style>
