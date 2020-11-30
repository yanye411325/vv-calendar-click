/* eslint-disable no-console */
<template>
  <div class="app">
    {{title}}
    <Calendar
      v-model="selectedDate"
      :select-date-change="onSelectDateChange"
      :config-day-data="calendarConfigDayData"
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
        { date: 1606196440525, numberCount: 1 },
        { date: 1606089600000, numberCount: 1 }
      ],
    };
  },
  methods: {
    onSelectDateChange(date) {
      this.selectedDate = date.date.timeString;
      console.log(`${date}`);
      console.log(`${this.selectedDate}`);
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
