<template>
  <div>
    <range-date-picker
      type="month"
      :min-date="minDate"
      :max-date="maxDate"
      :show.sync="isShow"
      :defaultDate="currentDate"
      :isDate="true"
      @submit="handleSubmit"
    />
    <button @click="handleClick">handle click</button>
  </div>
</template>

<script>
import RangeDatePicker from '../../components/rangeDatePicker.vue'

export default {
  name: 'StudentForm',
  components: {
    RangeDatePicker,
  },
  data() {
    return {
      currentDate: [new Date(2020, 11, 3), new Date(2020, 11, 3)],
      isShow: true,
      // 这里的 2 是 dateIndex 0 - 11
      minDate: new Date(2020, 8, 2),
      maxDate: new Date(2022, 11, 31),
    }
  },
  methods: {
    handleClick() {
      this.isShow = true
    },
    handleSubmit(...args) {
      console.log(...args)
    },
  },
}
</script>

<style></style>
