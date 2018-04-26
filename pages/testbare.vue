<template lang="html">
  <div >
    <BarChart></BarChart>
{{ headline }}

  </div>

</template>

<script>
import BarChart from '~/components/bar-chart.js'
export default {
  components: {
    BarChart
  },
  inheritAttrs: false,
  props: {
    headline: {
      type: String,
      default: 'Type'
    }
  }
}
</script>

<style lang="css">
</style>
