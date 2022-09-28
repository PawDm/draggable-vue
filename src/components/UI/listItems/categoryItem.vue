<template>
  <div>
    <div class="category-item">
      <div class="category-item__content">
        <button class="category-item__dropdown" @click="toogleVisibleDocument">
          <img
            v-if="!showDocuments"
            class="icon"
            :src="require(`@/assets/icons/down.svg`)"
          />
          <img v-else class="icon" :src="require(`@/assets/icons/up.svg`)" />
        </button>
        <div class="category-item__ttl">{{ category.name }}</div>
        <div class="category-item__lbl">{{ category.desc }}</div>
      </div>
      <div class="category-item__controls">
        <item-controls :item="category" />
      </div>
    </div>
    <div class="documents-list-in-category">
      <draggable handle=".handle" :group="{ name: 'row' }">
        <transition-group name="slide-fade">
          <document-item
            v-show="showDocuments"
            v-for="document in category.documents"
            :key="document.id"
            :document="document"
          />
        </transition-group>
      </draggable>
    </div>
  </div>
</template>

<script>
import documentItem from "./documentItem.vue"
import ItemControls from "./itemControls.vue"
import draggable from "vuedraggable"
export default {
  components: { documentItem, ItemControls, draggable },
  name: "CategoryItem",
  props: {
    category: {
      type: Object,
      required: true,
    },
  },
  data() {
    return {
      showDocuments: false,
    }
  },
  methods: {
    toogleVisibleDocument() {
      this.showDocuments = !this.showDocuments
    },
    check() {
      console.log("sda")
    },
  },
}
// Разобраться с  анимацией кнопки крестик в поиске, поиски драг энд дроп
</script>

<style lang="stylus" scoped>
.category-item
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
    font-weight: 500
    font-size: 15px
    padding 0 15px
  &__lbl
    font-style: normal
    font-weight: 400
    font-size: 11px
    color #8E9CBB
  &__dropdown
    background: #FFFFFF
    width 22px
    height: 22px
    border: 1px solid #D3D8DF
    border-radius: 50px
    display flex
    justify-content center
    align-items center
    cursor pointer
    &:hover
      filter drop-shadow(0px 4px 4px rgba(0, 0, 0, 0.25))
  &__controls
    justify-self flex-end
.documents-list-in-category
  margin-left 16px
.slide-fade-enter-active
  transition: all .6s ease
.slide-fade-leave-active
  transition: all .6s ease
.slide-fade-enter
  transform: translateY(-15px);
  opacity: 0
.slide-fade-leave-to
  transform: translateY(-15px);
  opacity: 0;
.sortable-ghost
  border-bottom: 4px solid blue;
  font-size: 0;
  overflow: hidden;
.drop-zone
  display block
  height 2px
  margin 0 -15px
</style>
