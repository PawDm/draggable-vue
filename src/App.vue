<template>
  <div id="app">
    <container />
  </div>
</template>

<script>
import container from "./components/container.vue"
export default {
  components: { container },
  name: "App",
}
</script>

<style lang="stylus">
#app
  font-family Fira Sans
  -webkit-font-smoothing antialiased
  -moz-osx-font-smoothing grayscale
  color #000
// .ghost-ticket
//   opacity 0.4
  // border-bottom: 4px solid blue;
.chosen-ticket
  border: 1px solid #DFE4EF
  box-shadow: 0px 3px 16px rgba(0, 102, 255, 0.7)
.dragging-ticket
  border: 1px solid #DFE4EF
  box-shadow: 0px 3px 16px rgba(0, 102, 255, 0.7)
</style>
