<template>
  <div class="document-item">
    <div class="document-item__content">
      <div class="document-item__ttl">{{ document.name }}</div>
      <div class="document-item__lbl">{{ document.desc }}</div>
    </div>
    <div class="document-item__controls">
      <item-controls :item="document" />
    </div>
  </div>
</template>

<script>
import ItemControls from "./itemControls.vue"
export default {
  name: "DocumentItem",
  components: {
    ItemControls,
  },
  props: {
    document: {
      type: Object,
      requred: true,
    },
  },
}
</script>

<style lang="stylus" scoped>
.document-item
  display flex
  flex-direction row
  align-items center
  width: 100%
  background: #FFFFFF
  border: 1px solid #DFE4EF
  height: 48px
  padding-left 16px
  cursor pointer
  &__content
    display flex
    flex-direction row
    align-items center
    width: 100%
  &__ttl
    font-weight: 400
    font-size: 13px
    padding-right 15px
  &__lbl
    font-style: normal
    font-weight: 400
    font-size: 11px
    color #8E9CBB
.sortable-ghost
  border-bottom: 4px solid blue;
  font-size: 0;
  overflow: hidden;
</style>
