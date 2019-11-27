<template lang="pug">
  .specifications
    .row.q-pb-lg
      .col
        .text-h5.text-bold Характеристики
    .row.q-pb-lg
      .col
        span Описание зала
          textarea.q-pa-sm.text-grey-8(
            v-model="roomDescription"
            type="textarea"
            rows=5
            style="width: 100%;"
          )
    .row.q-pb-lg
      .col.q-pr-sm
        span Высота потолков, м
        q-input(v-model="roomHeight" outlined dense)
      .col
        span(style="line-height: 0;") Площадь, м
          sup 2
        q-input(v-model="roomYardage" outlined dense)
    abstract-list(:dataArray="characteristics")

</template>

<script>
import AbstractList from './AbstractDataList/abstractList'
export default {
  name: 'specifications',
  components: { AbstractList },
  props: {
    description: {
      type: String,
      default: _ => 'Новый зал'
    },
    height: {
      type: Number,
      default: _ => 1
    },
    yardage: {
      type: Number,
      default: _ => 1
    },
    characteristics: {
      type: Array,
      default: _ => []
    }
  },
  data: () => ({
    itemsCount: 6,
    roomHeight: 0,
    roomYardage: 0,
    roomDescription: '',
    isCharacteristics: true
  }),
  created () {
    this.roomHeight = this.height
    this.roomYardage = this.yardage
    this.roomDescription = this.description
  }
}
</script>
