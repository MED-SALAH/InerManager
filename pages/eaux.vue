<template lang="html">
  <v-layout row wrap>
    <v-flex>
      <div >
        <LineChart :data="datatou" :options="options"></LineChart>

      </div>
    </v-flex>

    <v-flex text-xs-center xs12 md3 class="ma-3">
      <v-card>
        <TestBare></TestBare>
        <v-divider></v-divider>
        <v-card-actions>
        <v-btn flat color="info">Plus De Détail</v-btn>
        </v-card-actions>
      </v-card>
    </v-flex>
  </v-layout>


</template>

<script>
import LineChart from '~/components/line-chart.js'
import TestBare from '~/components/testbare.vue'

export default {
  components: {
    LineChart,
    TestBare
  },
  data () {
    return {
      datatou: {
        labels: ['January', 'February', 'March', 'April', 'May', 'June', 'July', 'August', 'September', 'October', 'November', 'December'],
        datasets: [{
          label: 'Planifier',
          backgroundColor: '#ff8c00',
          data: [40, 20, 12, 39, 10, 40, 39, 80, 40, 20, 12, 11]
        }]
      },
      options: {
        maintainAspectRatio: false,
        scales: {
          yAxes: [{
            display: true,
            ticks: {
              beginAtZero: true,
              min: 0,
              max: 100,
              stepSize: 10,
              callback: function (label, index, labels) {
                return label + ' %' // just change the '$' to % for percentage
              }
            },
            gridLines: {
              display: true
            }
          }],
          xAxes: [ {
            display: false,
            gridLines: {
              display: false
            }
          }]
        }
      }
    }
  }
}
</script>

<style lang="css">
</style>
