# vv-calendar

> 基于vv-calendar的click优化版



## install

npm install vv-calendar-click -s

## how to use

属性

| name          | type   | Value                                          |
| ------------- | ------ | ---------------------------------------------- |
| type          | string | month / week，分别代表显示周、月，和只显示周。 |
| configDayData | array  | 在某些天上需要加上的标识数据                   |

| name             | type     | arguments | callback                   |
| ---------------- | -------- | --------- | -------------------------- |
| selectDateChange | function | date      | 返回当前选中的日期相关数据 |

```javascript
import Vue from "vue";
import Calendar from "vv-calendar";
Vue.use(Calendar);
```

```html
<Calendar
  v-model="selectedDate"
  :config-day-data="calendarConfigDayData"
  type="month"
></Calendar>
```
```javascript
 data() {
    return {
      selectedDate: new Date(),
      calendarConfigDayData: [
        { date: 1586706786234, numberCount: 3 }
      ],
    };
  },
  methods: {
    onSelectDateChange(date) {
      this.selectedDate = date.date.timeString;
      console.log(date);
      console.log(this.selectedDate);
    },
  }
```


