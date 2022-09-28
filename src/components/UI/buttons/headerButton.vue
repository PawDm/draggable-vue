<template>
  <button class="header-button">
    <div class="header-button__icon">
      <img class="icon" :src="require(`@/assets/icons/${icon}.svg`)" />
    </div>
    <div v-if="text" class="header-button__lbl">{{ text }}</div>
  </button>
</template>

<script>
export default {
  name: "HeaderButton",
  props: {
    text: {
      type: String,
      required: false,
      default: "",
    },
    icon: {
      type: String,
      required: true,
    },
  },
}
</script>

<style lang="stylus" scoped>
.header-button
  display flex
  align-items center
  cursor pointer
  border: 1px solid #D3D8DF
  border-radius: 50px
  padding 0 10px
  margin: 0 5px
  background #fff
  &:hover
    filter drop-shadow(0px 4px 4px rgba(0, 0, 0, 0.25))
  &__icon
    height: 30px
    display flex
    justify-content center
    align-items: center
  &__lbl
    padding 0 10px
    font-size 12px
    font-weight 500
</style>
