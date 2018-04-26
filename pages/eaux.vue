<template lang="html">
  <div >
    <LineChart></LineChart>


  </div>

</template>

<script>
import LineChart from '~/components/line-chart.js'
export default {
  components: {
    LineChart
  },
  data () {
    return {
      mywidth: 300,
      myheight: 500
    }
  }
}
</script>

<style lang="css">
</style>
