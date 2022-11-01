<template>
  <!-- aria-hidden="true" 可有可无 -->
  <svg :class="svgClass" aria-hidden="true" v-on="$listeners">
    <use :href="iconName" />
  </svg>
</template>

<script>
export default {
  name: 'SvgIcon',
  props: {
    iconClass: {
      type: String,
      required: true
    },
    className: {
      type: String,
      default: ''
    }
  },
  computed: {
    // svg图标名称
    iconName() {
      return `#myicon-${this.iconClass}`
    },
    // 添加新类名、增加样式
    svgClass() {
      if (this.className) {
        return `svg-icon ${this.className}`
      }
      return 'svg-icon'
    }
  }
}
</script>

<style scoped>
.svg-icon {
  width: 1em;
  height: 1em;
  vertical-align: -0.15em;
  fill: currentColor;
  overflow: hidden;
}
</style>
