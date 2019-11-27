<template lang="pug">
  .data
    .row(v-if="showPart")
      // Модификация объекта!!!!!!!
      .col-6(v-for="(item, index) in dataArray" :key="index")
        q-checkbox(v-if="index < itemsCount" v-model="item.isChecked" :label="item.name")
    .row.q-pb-lg(v-if="showPart")
      .col.cursor-pointer(@click="showPart=!showPart")
        .text-h6.text-primary Показать все
    .row(v-if="!showPart")
      // Модификация объекта!!!!!!!
      .col-6(v-for="(item, index) in dataArray" :key="index")
        q-checkbox(v-model="item.isChecked" :label="item.name")
    .row.q-pb-lg(v-if="!showPart")
      .col.cursor-pointer(@click="showPart=!showPart")
        .text-h6.text-primary Скрыть
</template>

<script>
export default {
  name: 'abstractList',
  props: {
    dataArray: {
      type: Array,
      default: _ => []
    }
  },
  data: () => ({
    itemsCount: 6,
    showPart: true
  })
}
</script>
