<template>
  <div class="header">
    <h2>Документы</h2>
    <div class="header__controls">
      <header-button :icon="'favorites'" />
      <header-button :icon="'plus'" :text="'Новый тип'" />
      <header-button :icon="'plus'" :text="'Новый документ'" />
    </div>
  </div>
</template>

<script>
import HeaderButton from "./UI/buttons/headerButton.vue"
export default {
  name: "Header-menu",
  components: {
    HeaderButton,
  },
}
</script>

<style lang="stylus" scoped>
.header
  display flex
  justify-content space-between
  width 100%
  h2
    margin 0
    font-weight: 500
    font-size: 22px
    line-height: 108%
    font-style normal
  &__controls
    display flex
    flex-direction row
    padding-right 45px
</style>
