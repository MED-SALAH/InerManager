<template lang="html">
  <div >
    <RadarChart></RadarChart>


  </div>

</template>

<script>
import RadarChart from '~/components/radar-chart.js'
export default {
  components: {
    RadarChart
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
