<template>
  <div class="hello">
    <h1>Mars的组件练习</h1>
    <clock-exe></clock-exe>
  </div>
</template>

<script>
import clockExe from './clock'
export default {
  name: 'marshome',
  components:{
    clockExe
  }
}
</script>