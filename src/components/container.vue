<template>
  <div class="container">
    <header-menu />
    <div class="content">
      <search-input />
      <list-items :categories="categories1" />
      <!-- <main-area :categories="categories" /> -->
    </div>
  </div>
</template>

<script>
import headerMenu from "./headerMenu.vue"
// import MainArea from "./mainArea.vue"
import ListItems from "./listItems.vue"
import SearchInput from "./UI/inputs/searchInput.vue"
export default {
  components: { headerMenu, SearchInput, ListItems },
  name: "Container",
  data() {
    return {
      categories1: [
        {
          id: 0,
          name: "without",
          documents: [
            {
              id: 1,
              name: "item 5",
            },
            {
              id: 2,
              name: "item 9",
            },
          ],
        },
        {
          id: 1,
          name: "main",
          documents: [
            {
              id: 3,
              name: "item 2",
            },
            {
              id: 4,
              name: "item 3",
            },
          ],
        },
        {
          id: 2,
          name: "other",
          documents: [
            {
              id: 5,
              name: "item 1",
            },
          ],
        },
        {
          id: 3,
          name: "special",
          documents: [],
        },
      ],
      categories: [
        {
          id: 0,
          name: "without",
          documents: [
            {
              title: "item 5",
            },
            {
              title: "item 9",
            },
          ],
        },
        {
          id: 1,
          name: "main",
          items: [
            {
              title: "item 2",
            },
            {
              title: "item 3",
            },
          ],
        },
        {
          id: 2,
          name: "other",
          items: [
            {
              title: "item 1",
            },
          ],
        },
        {
          id: 3,
          name: "special",
        },
      ],
      // categories: [
      //   {
      //     id: 1,
      //     name: "Обязательные для всех",
      //     desc: "Документы, обязательные для всех сотрудников без исключения",
      //     documents: [
      //       {
      //         id: 100,
      //         name: "Пасспорт",
      //         desc: "Пасспорт гражданина",
      //       },
      //       {
      //         id: 101,
      //         name: "Жопа",
      //         desc: "Жопа гражданина",
      //       },
      //     ],
      //   },
      //   {
      //     id: 2,
      //     name: "Обязательные для трудоустройства",
      //     desc: "Документы, без которых невозможно трудоустройство человека на какую бы то ни было должность в компании вне зависимости от гражданства",
      //     documents: [
      //       {
      //         id: 201,
      //         name: "Пасспорт",
      //         desc: "Пасспорт гражданина",
      //       },
      //       {
      //         id: 202,
      //         name: "Жопа",
      //         desc: "Жопа гражданина",
      //       },
      //     ],
      //   },
      //   {
      //     id: 3,
      //     name: "Специальные",
      //     desc: "",
      //     documents: [],
      //   },
      //   {
      //     id: 0,
      //     name: "Без категории",
      //     desc: "",
      //     documents: [
      //       {
      //         id: 901,
      //         name: "Бумажка 1",
      //         desc: "бумажка 1 гражданина",
      //       },
      //       {
      //         id: 902,
      //         name: "Бумажка 2",
      //         desc: "бумажка 2 гражданина",
      //       },
      //     ],
      //   },
      // ],
    }
  },
}
</script>

<style lang="stylus" scoped>
.container
  width 100%
  display flex
  flex-direction column
  .content
    padding 29px 31px 0px 31px
</style>
