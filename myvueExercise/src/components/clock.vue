/*
 * @Desc: 文件名 
 * @Example: '' 
 * @Author: 任瀚汶
 * @Date: 2020-07-19 10:26:58 
 * @Last Modified by: 任瀚汶
 * @Last Modified time: 2020-07-20 08:58:05
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
    //用setInterval方法实现

    // interval = setInterval(() =>{
    //   let icnow = new Date();
    //   this.year = icnow.getFullYear();
    //   this.month = icnow.getMonth() + 1;
    //   this.date = icnow.getDate();
    //   // this.day = days[icnow.getDay()];
    //   this.day = icnow.getDay();
    //   this.time = icnow.toTimeString().substring(0, 8);
    //   console.log(icnow)
    // }, 1000)
    
    function setTime(second,fn){
      let timeOut = (second,fn)=>{
          setTimeout(()=>{
            fn();
            timeOut(second,fn);
          },second)
      }
      timeOut(second,fn);
    }

    setTime(1000,()=>{
      let icnow = new Date();
      this.year = icnow.getFullYear();
      this.month = icnow.getMonth() + 1;
      this.date = icnow.getDate();
      this.day = icnow.getDay();
      this.time = icnow.toTimeString().substring(0, 8);
      console.log(icnow)
    })
  }
}
</script>

<style scoped>
  .hello{
    border: 1px solid red;
  }
</style>