/* eslint-disable no-console */
<template>
  <div class="app">
    {{title}}
    <Calendar
      v-model="selectedDate"
      :select-date-change="onSelectDateChange"
      :config-day-data="calendarConfigDayData"
      @monthChange="monthChange"
      type="month"
    />
  </div>
</template>

<script>
import moment from 'moment'
// import Calendar from "../dist/calendar"; 
import Calendar from "./components/calendar"
export default {
  name: "App",
  components: {
    Calendar,
  },
  data() {
    return {
      title: '',
      selectedDate: new Date(),
      calendarConfigDayData: [
        { date: 1586706786234, numberCount: 3 },
        { date: 1585842786000, numberCount: 1 },
        { date: 1586361186000, numberCount: 2 },
        { date: 1586351186000, numberCount: 21640 }
      ],
    };
  },
  methods: {
    onSelectDateChange(date) {
      this.selectedDate = date.date.timeString;
      console.log(date);
      console.log(this.selectedDate);
    },
    onCalendarChangeDatePage(startDate, endDate) {
      console.log(startDate, endDate);
    },
    monthChange(currentMoment) {
      // 月切换 当月取当前日期
      // const nowMonth = moment().format('YYYY年MM月')
      const emitMonth = moment(currentMoment).format('YYYY年MM月')
      // console.log(emitMonth)
    }
  }
};
</script>

<style>
* {
  touch-action: none;
}
.app {
  margin: 0;
  padding: 0;
}
</style>
