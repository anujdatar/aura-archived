<template>
  <div class="card" :style="cardStyle">
    <slot />
  </div>
</template>

<script>
export default {
  props: {
    width: {
      type: String,
      default: ''
    },
    height: {
      type: String,
      default: ''
    },
    color: {
      type: String,
      default: ''
    },
    bgColor: {
      type: String,
      default: ''
    }
  },
  computed: {
    cardStyle () {
      const style = {}
      if (this.width !== '') {
        style['--width'] = this.width
      }
      if (this.height !== '') {
        style['--height'] = this.height
      }
      if (this.color !== '') {
        style['--color'] = this.color
      }
      if (this.bgColor !== '') {
        style['--bg-color'] = this.bgColor
      }
      return style
    }
  }
}
</script>

<style>
.card {
  color: var(--color, green);
  background: var(--bg-color);

  width: var(--width);
  height: var(--height);

  display: flex;
  flex-wrap: wrap-reverse;
}
</style>
