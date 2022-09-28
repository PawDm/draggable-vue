<template>
  <button class="control-button" @click="$emit('click')">
    <img :src="require(`@/assets/icons/${icon}.svg`)" />
  </button>
</template>

<script>
export default {
  name: "ControlButton",
  props: {
    icon: {
      type: String,
      required: true,
    },
  },
}
</script>

<style lang="stylus" scoped>
.control-button
  border none
  background #fff
  cursor pointer
  margin 0 4px
</style>
