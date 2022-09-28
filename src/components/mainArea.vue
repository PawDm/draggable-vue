<template>
  <div class="main-area">
    <draggable handle=".handle">
      <category
        v-for="category in categories.filter((item) => item.id !== 0)"
        :key="category.id"
        :category="category"
      />
    </draggable>
    <div class="others">
      <draggable handle=".handle" :group="{ name: 'row' }">
        <div class="item" v-for="(item, index) in withoutCategory" :key="index">
          <div>{{ item.title }}</div>
          <button class="handle">move</button>
        </div>
      </draggable>
    </div>
  </div>
</template>

<script>
import draggable from "vuedraggable"
import category from "./testComponents/category.vue"
export default {
  components: { category, draggable },
  name: "MainArea",
  props: {
    categories: {
      type: Array,
      required: true,
    },
  },
  computed: {
    withoutCategory() {
      const category = this.categories.find((item) => item.id === 0)
      return category.items
    },
  },
}
</script>

<style lang="stylus" scoped>
.main-area
  margin-top 35px
  display flex
  flex-direction column
  width 100%
.others
  display block
  height 2px
  margin-top 20px
.item
  border 1px solid grey
  padding: 3px
  margin-bottom 2px
  display flex
  flex-direction: row
  justify-content: space-between
</style>
