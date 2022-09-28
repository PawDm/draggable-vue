<template>
  <input
    class="search-input"
    type="search"
    v-model="value"
    placeholder="Поиск"
  />
</template>

<script>
export default {
  name: "SearchInput",
  data() {
    return {
      value: "",
    }
  },
}
</script>

<style lang="stylus" scoped>
input.search-input[type="search"]
  display block
  padding 0px
  padding-left 26px
  padding-bottom 10px
  width: 564px
  height 30px
  border none
  border-bottom 1px solid #BFC9E0
  background-color: white
  background-image: url('../../../assets/icons/search.svg')
  background-position: 0 0
  background-repeat: no-repeat
  font-family Fira Sans
  font-size 15px
  &::placeholder
    font-style italic
    font-size 15px
  &:focus
    outline: none
    border-bottom 1px solid #0066FF
</style>
