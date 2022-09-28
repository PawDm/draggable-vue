<template>
  <div class="item-controls">
    <control-button :icon="'edit'" />
    <control-button :icon="'delete'" />
    <control-button class="handle" @click="moveItem" :icon="'move'" />
  </div>
</template>

<script>
import controlButton from "../buttons/controlButton.vue"
export default {
  components: { controlButton },
  name: "ItemControls",
  props: {
    item: {
      type: Object,
      required: true,
    },
  },
  methods: {
    moveItem() {
      console.log(this.item)
    },
  },
}
</script>

<style lang="stylus" scoped>
.item-controls
  display flex
  flex-direction row
  height: 100%
  padding-right 5px
</style>
