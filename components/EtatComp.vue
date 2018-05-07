<template lang="html">
    <v-card color="pink lighten-5">
      <v-container>
        <v-layout row wrap>
          <v-flex xs6 offset-xs1>
            <v-icon x-large :class="color">{{ nicon }}</v-icon>
          </v-flex>
          <v-flex xs4 class="text-xs-center">
              <strong>{{text}}</strong><br>
              <strong><h2>{{valeur1}}</h2></strong>
          </v-flex>
        </v-layout>
      </v-container>
      <v-divider></v-divider>
    <div class="text-xs-center">
      <strong>{{valeur2}}</strong>
    </div>
    </v-card>
</template>

<script>
export default {
  props: {
    nicon: {
      type: String,
      default: ''
    },
    text: {
      type: String,
      default: ''
    },
    color: {
      type: String,
      default: 'primary'
    },
    valeur1: {
      type: Number,
      default: 0
    },
    valeur2: {
      type: String,
      default: ''
    }
  }
}
</script>

<style lang="css">
</style>
