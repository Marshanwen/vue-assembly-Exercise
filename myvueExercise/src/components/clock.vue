/*
 * @Desc: 文件名 
 * @Example: '' 
 * @Author: 任瀚汶
 * @Date: 2020-07-19 10:26:58 
 * @Last Modified by: 任瀚汶
 * @Last Modified time: 2020-07-19 10:27:18
*/
<template>
  <div class="hello">
    this is a clock component
    <p>现在的时间是{{ year }}.{{month}}.{{date}} {{time}}</p>
  </div>
</template>
<script>

let icnow = new Date();      // 初始化时间
let interval; 
export default {
  data() {
    return {
      year: icnow.getFullYear(),
      month: icnow.getMonth() + 1,
      date: icnow.getDate(),
      day: icnow.getDay(),
      time: icnow.toTimeString().substring(0, 8),
    }
  },
  created () {
    interval = setInterval(() =>{
      let icnow = new Date();
        this.year = icnow.getFullYear();
        this.month = icnow.getMonth() + 1;
        this.date = icnow.getDate();
        // this.day = days[icnow.getDay()];
        this.day = icnow.getDay();
        this.time = icnow.toTimeString().substring(0, 8);
        console.log(icnow)
    }, 1000)
  },
  computed: {
            // 当前时间
	 newTime: function () {
              return this.year + '年' + this.month + '月' + this.date + '日 星期' + this.day + ' ' + this.time;
      }
  },
  beforeDestroy () {
    clearInterval(interval);
  }
}
</script>

<style scoped>
  .hello{
    border: 1px solid red;
  }
</style>