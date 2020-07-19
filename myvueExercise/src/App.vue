<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'App',
  computed: {
    count () {
      return this.$store.state.count
    }
  },
}
</script>
