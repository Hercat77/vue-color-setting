# Vue Color Gradient Picker

## Table of Contents

* [Installation](#installation)
* [Examples](#examples)
* [Demos](#demo)

## Installation

To install, you can use [npm](https://npmjs.org/) or [yarn](https://yarnpkg.com):


    $ npm install vue-color-setting --save
    
## Examples

Here is a simple examples of react-color-gradient-picker being used in an app:

### Color Picker && Gradient Color Picker
```vue
<template>
  <div id="app">
    <ColorPicker
      :color="color"
      :is-gradient="isShowGradient"
      :onStartChange="color => onChange(color, 'start')"
      :onChange="color => onChange(color, 'change')"
      :onEndChange="color => onChange(color, 'end')"
    />
  </div>
</template>

<script>
import { ColorPicker } from 'vue-color-gradient-picker';

export default {
  name: 'App',

  components: {
    ColorPicker
  },

  data()  {
    return {
      color: {
        red: 255,
        green: 0,
        blue: 0,
        alpha: 1
      },
      isShowGradient: false
    }
  },   

  methods: {
    onChange(attrs, name) {
      this.color = { ...attrs };
      if (!attrs.type) return
      this.isShowGradient = attrs.type != 'solid';
    }
  }
}
</script>

<style src="vue-color-gradient-picker/dist/index.css" lang="css" />
```
## Demo

* [Solid and gradient pickers live demo](https://arthay.github.io/vue-color-setting/)
