<template>
  <div id="app" :style="{ display: 'flex', textAlign: 'center' }">
    <!--<div>
      <ColorPicker
          :color="color"
          :onStartChange="color => onChange(color, 'start')"
          :onChange="color => onChange(color, 'change')"
          :onEndChange="color => onChange(color, 'end')"
      />
    </div>-->
    <div>
      <ColorPicker
          :color="color"
          :is-gradient="isShowGradient"
          :onStartChange="color => onChange(color, 'start')"
          :onChange="color => onChange(color, 'change')"
          :onEndChange="color => onChange(color, 'end')"
      />
    </div>
  </div>
</template>

<script>
import { ColorPicker } from './lib'

export default {
  name: 'App',
  components: {
    ColorPicker
  },

  data() {
    return {
      color: {
        red: 255,
        green: 0,
        blue: 0,
        alpha: 1
      },
      isShowGradient: false
    };
  },

  methods: {
    onChange(attrs,name) {
      console.log(attrs, name);
      this.color = { ...attrs };
      if (!attrs.type) return
      this.isShowGradient = attrs.type != 'solid';
    }
  }
}
</script>

<style src="@/lib/index.scss" lang="scss" />
