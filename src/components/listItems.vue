<template>
  <div class="list-items">
    <draggable @start="start" handle=".handle" ghostClass="ghost-ticket">
      <category-item
        v-for="category in categories.filter((item) => item.id !== 0)"
        :key="category.id"
        :category="category"
      />
    </draggable>
    <div class="other-documents">
      <draggable
        @start="start"
        @end="end"
        handle=".handle"
        :group="{ name: 'row' }"
      >
        <document-item
          v-for="(document, index) in withoutCategory"
          :key="document.id"
          :document="document"
          :class="[dragged_index === index ? '' : 'jopa']"
        />
      </draggable>
    </div>
  </div>
</template>

<script>
import categoryItem from "./UI/listItems/categoryItem.vue"
import DocumentItem from "./UI/listItems/documentItem.vue"
import draggable from "vuedraggable"
export default {
  components: { categoryItem, draggable, DocumentItem },
  name: "ListItems",
  props: {
    categories: {
      type: Array,
      required: true,
    },
  },
  data() {
    return {
      dragged_index: null,
      is_dragging: false,
    }
  },
  computed: {
    withoutCategory() {
      const category = this.categories.find((item) => item.id === 0)
      return category.documents
    },
  },
  methods: {
    start(event) {
      console.log(event)
      console.log("start")
      this.is_dragging = true
      this.dragged_index = event.oldIndex
    },
    end(event) {
      console.log(event)
      console.log("end")
      this.is_dragging = true
      this.dragged_index = event.oldIndex
    },
  },
}
// возможно не нужно пихать одно в другое, и тогда будет работать нормальн
</script>

<style lang="stylus">
.list-items
  padding-top 35px
  display flex
  flex-direction: column
  .other-documents
    display block
    height 2px
    margin-top 20px
.on-drag
  background-color red
</style>
