## 启动在线开发

- online-dev start

## 推送组件

- online-dev push

## freeConfig 配置描述

```javascript
export default {
  /**
   * 根标签布局
   * 属性支持:
   *  width     宽度
   *  height    高度
   *  top       上边距
   *  left      左边距
   *  position  绝对定位
   *  zIndex    层级
   */
  rootTagLayout: {
    //...
    width: "120px",
    height: "120px",
  },

  /**
   * 自由样式
   * 属性:  自定义key
   */
  freeStyle: {
    fontColor: {
      // 属性描述
      label: "字体颜色",

      // 对应的style属性
      type: "color",

      // 默认数据
      defaultValue: "#000000",
    },
  },

  /**
   * 自由数据
   * 属性:  自定义key
   */
  freeData: {
    text: {
      // 属性描述
      label: "文本内容",

      // 更新模式
      // 【promise, object, string, number, boolean】
      updateMode: "string",

      // 提供选择的数据只在updateMode为string/number/boolean有效
      // value类型为string/number/boolean
      // {label:"",value:""}
      selectData: [],

      // 更改数据时校验函数
      validation: function (data) {},

      // 默认数据，数据类型与updateMode一致
      defaultValue: "hello world!",
    },
  },

  /**
   * 自由绑定函数
   * 属性:  自定义函数名
   */
  freeBindMethods: {
    funcName: {
      // 函数描述
      describe: "",

      // 默认函数
      defaultFunc: function (...paramet) {
        console.log(paramet);
      },
    },
  },
};
```

## 按需加载【以 element-ui 为例】

```javascript
// 第一步 安装依赖
npm i element-ui -S
npm i babel-plugin-component -D

```

- 在根目录添加.babelrc ，添加内容配置

```javascript
{
	"plugins": [
		[
			"component",
	    	{
				"libraryName": "element-ui",
				"styleLibraryName": "theme-chalk"
			}
		]
	]
}
```

- .vue 中引用

```javascript
<script>
import { Button } from 'element-ui'
export default {
	// 方式1
	components:{
		"el-button": Button
	},
	// 方式2
	use:{
		Button
	},
	// ...
};
</script>
```
