# SmButton 组件

### 介绍

SmButton 是一个按钮组件

### 引入

```javascript
import Vue from 'vue';
import { SmButton } from 'sm-form-library';

Vue.use(SmButton);
```

## 代码演示

### 基础用法

```html
<template>
  <sm-button @onclick="handleClick"></sm-button>
</template>

<script lang='ts' setup>
const handleClick = () => {
  console.log('123');
}
</script>
```

### 禁用按钮

```html
<template>
  <sm-button :permission="permission" ></sm-button>
</template>

<script lang='ts' setup>
const permission = ['readonly'];
</script>
```

### 按钮文本内容

```html
<template>
  <sm-button title="按钮文本内容"></sm-button>
</template>

```

### 带图标的按钮

```html
<template>
  <sm-button :icon="icon"></sm-button>
</template>

<script lang='ts' setup>
const icon= 'setting-o',
</script>
```

### 下拉按钮

```html
<template>
  <sm-button :dropDownButton="options" @onitemclick="itemClick"></sm-button>
</template>

<script lang='ts' setup>
const options1 = reactive({
  type: 1,
  items: [
    { name: '羽毛球', value: '0' },
    { name: '篮球', value: '1' },
    { name: '毽球', value: '2' },
    { name: '网球', value: '3' },
    { name: '游泳', value: '4' },
  ],
});
const itemClick = (item,index) =>{
  console.log(item, index);
}
</script>
```

## API

### Props

| 属性           | 说明                   | 类型             | 默认值     | 备注                          |
| -------------- | ---------------------- | ---------------- | ---------- | ----------------------------- |
| title          | 标题(按钮文本内容)     | _String_         | `按钮`     |                               |
| icon           | 左侧图标名称或图片链接 | _String_         |            |                               |
| color          | 按钮颜色               | _String_         | `#3B86E0`  |                               |
| textColor      | 按钮文字颜色           | _String_         | `#ffffff`  |                               |
| width          | 按钮显示的宽度         | _String, Number_ | `100`      |                               |
| widthUnit      | 按钮显示的宽度单位     | _String_         | `%`        | 单位有百分比（%）、像素（px） |
| height         | 按钮显示的高度         | _String, Number_ | `48`       |                               |
| heightUnit     | 按钮显示的高度单位     | _String_         | `px`       | 单位有像素（px）              |
| permission     | 权限控制，可多选       | _Array_          | `['edit']` |                               |
| dropDownButton | 下拉菜单数据           | _Object_         | -          |                               |

### Events

| 方法名        | 说明               | 参数                     |
| ------------- | ------------------ | ------------------------ |
| onclick       | 按钮点击事件       |                          |
| onitemclick   | 菜单每一项点击事件 | 点击项的值，点击项的索引 |
