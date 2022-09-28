<template>
  <div>
    <div class="category">
      <div>{{ category.name }}</div>
      <button class="handle">move</button>
    </div>
    <div class="items">
      <draggable handle=".handle" :group="{ name: 'row' }">
        <div class="item" v-for="(item, index) in category.items" :key="index">
          <div>{{ item.title }}</div>
          <button class="handle">move</button>
        </div>
      </draggable>
    </div>
  </div>
</template>

<script>
import draggable from "vuedraggable"
export default {
  name: "Category",
  components: { draggable },
  props: {
    category: {
      type: Object,
      required: true,
    },
  },
}
</script>

<style lang="stylus" scoped>
.category
  border 1px solid #000
  display flex
  flex-direction: row
  justify-content: space-between
  padding 5px
  margin-bottom 3px
.items
  display flex
  flex-direction column
  padding-left 15px
.item
  border 1px solid grey
  padding: 3px
  margin-bottom 2px
  display flex
  flex-direction: row
  justify-content: space-between
.sortable-ghost
  border-bottom: 4px solid blue;
  font-size: 0;
  overflow: hidden;
.sortable-chosen
  background-color red
</style>
