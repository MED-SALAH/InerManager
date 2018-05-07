<template>
  <v-layout row wrap>
      <v-flex xs12 md3 v-for="item in Etcom" row wrap class="ma-3">
        <EtatComp :color='item.color' :nicon="item.mcon" :text="item.texte" :valeur1="item.val1" :valeur2="item.val2"></EtatComp>
      </v-flex>
      <v-flex xs12 md3 v-for='item in items' text-xs-center d-flex sm3 class="ma-3">
                  <v-card color="gray">
                    <v-flex xs8 offset-xs1>
                      <h2>{{ item.titrecom }}</h2>
                      <Doughnout :data="item.datadou" :options="item.options">
                      </Doughnout>
                    </v-flex>
                    <v-flex xs3 offset-xs1>
                      <span>{{item.unit}}</span>
                    </v-flex>
                    <v-card-actions>
                    <v-btn outline color="deep-orange">Plus De Détail</v-btn>
                    </v-card-actions>
                  </v-card>
       </v-flex>
  </v-layout>

</template>

<script>
import Doughnout from '~/components/doughnut-chart.js'
import EtatComp from '~/components/EtatComp.vue'

export default {
  components: {
    Doughnout,
    EtatComp
  },
  data () {
    return {
      Etcom: [
        {color: 'red--text', mcon: 'home', texte: 'Entreprises', val1: 3, val2: 'Entreprise'},
        {color: 'teal--text lighten-4', mcon: 'event', texte: 'Zones', val1: 13, val2: 'Zones'},
        {color: 'purple--text darken-2', mcon: 'widgets', texte: 'Capteurs', val1: 100, val2: 'Capteurs installés'}
      ],
      items: [
        {
          titrecom: 'Consomation Electrique',
          unit: 'Kwh',
          datadou: {
            labels: ['Electricité'],
            datasets: [{
              label: 'OK',
              data: [23, 42],
              backgroundColor: ['#01B2FE'],
              hoverBackgroundColor: ['#0101E6']
            }]
          },
          options: {
            title: {
              display: true,
              position: 'bottom'
              // text: 'Consomation'
            },
            cutoutPercentage: 90
          }
        },
        {
          titrecom: 'Consomation Eaux',
          unit: 'Litre',
          datadou: {
            labels: ['Eaux'],
            datasets: [{
              label: 'OK',
              data: [18, 19],
              backgroundColor: ['#70F4F0'],
              hoverBackgroundColor: ['#6ACAED']
            }]
          },
          options: {
            title: {
              display: true,
              position: 'bottom'
              // text: 'Consomation'
            },
            cutoutPercentage: 50
          }
        },
        {
          titrecom: 'Consomation Gaz',
          unit: 'Kwh',
          datadou: {
            labels: ['Gaze'],
            datasets: [{
              label: 'OK',
              data: [42, 19],
              backgroundColor: ['#FE8787'],
              hoverBackgroundColor: ['#FE0101']
            }]
          },
          options: {
            title: {
              display: true,
              position: 'bottom'
              // text: 'Consomation'
            },
            cutoutPercentage: 0
          }
        },
        {
          titrecom: 'Confort De Votre Bati',
          datadou: {
            labels: ['confort'],
            datasets: [{
              label: 'OK',
              data: [80, 20],
              backgroundColor: ['#0D9354'],
              hoverBackgroundColor: ['#00542D']
            }]
          },
          options: {
            title: {
              display: true,
              position: 'bottom'
              // text: 'Consomation'
            },
            cutoutPercentage: 70
          }
        }
      ]
    }
  }
}
</script>
