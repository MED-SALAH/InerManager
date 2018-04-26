<template>
  <v-app>
    <v-toolbar
    color="blue darken-3"
      dark
      app
      fixed
      :clipped-left="clipped"
    >
      <v-toolbar-title style="width: 300px" class="white--text">
      <v-toolbar-side-icon @click.stop='drawer = !drawer'></v-toolbar-side-icon>

      <v-btn
        icon
        @click.stop="clipped = !clipped"
      >
        <v-icon>web</v-icon>
      </v-btn>

      <span>Nom-Societe ==></span>
      </v-toolbar-title>
      <nuxt-link to="/"><v-btn class="orange">Acceuil</v-btn></nuxt-link>
      <nuxt-link to="/Electricite"><v-btn class="orange">Electricite</v-btn></nuxt-link>
      <nuxt-link to="/eaux"><v-btn class="orange">Line</v-btn></nuxt-link>
      <nuxt-link to="/testradar"><v-btn class="orange">Radar</v-btn></nuxt-link>
      <nuxt-link to="/testbare"><v-btn class="orange">Bare</v-btn></nuxt-link>
      <nuxt-link to="/testdough"><v-btn class="orange">dough</v-btn></nuxt-link>




      <v-spacer></v-spacer>
      <nuxt-link to="/Autre"><v-btn class="orange">ICI</v-btn></nuxt-link>

      <v-btn icon>
                 <v-icon>search</v-icon>
               </v-btn>
     <v-text-field
       placeholder="Search..."
       single-line
       append-icon="search"
       :append-icon-cb="() => {}"
       color="white"
       hide-details
     ></v-text-field>

   <v-btn icon>
     <v-icon>apps</v-icon>
   </v-btn>
   <v-btn icon>
     <v-icon large color="grey lighten-1">notifications</v-icon>
   </v-btn>

    </v-toolbar>

    <v-navigation-drawer
    :clipped="clipped"
    v-model="drawer"
    fixed
    app
    >
      <v-list >
           <template v-for="item in items">
             <v-layout
               row
               v-if="item.heading"
               align-center
               :key="item.heading"
             >
           </v-layout>
           <v-list-group
             v-else-if="item.children"
             v-model="item.model"
             :key="item.text"
             :prepend-icon="item.model ? item.icon : item['icon-alt']"
             append-icon=""
           >
             <v-list-tile slot="activator">

               <v-list-tile-content>
                 <v-list-tile-title>
                   {{ item.text }}
                 </v-list-tile-title>
               </v-list-tile-content>
             </v-list-tile>


             <v-list-tile
               v-for="(child, i) in item.children"
               :key="i"
               @click=""
             >
              <v-list-tile-action v-if="child.icon">
                 <v-icon>{{ child.icon }}</v-icon>
               </v-list-tile-action>
               <v-list-tile-content>
                 <v-list-tile-title>
                   {{ child.text }}
                 </v-list-tile-title>
               </v-list-tile-content>
             </v-list-tile>
           </v-list-group>

             <v-list-tile v-else @click="" :key="item.text">
               <v-list-tile-action>
                 <v-icon>{{ item.icon }}</v-icon>
               </v-list-tile-action>
               <v-list-tile-content>
                 <v-list-tile-title>
                   {{ item.text }}
                 </v-list-tile-title>
               </v-list-tile-content>
             </v-list-tile>
           </template>
         </v-list>
    </v-navigation-drawer>



<v-content>
<v-container grid-list-xs,sm,md,lg,xl>
  <nuxt/>
</v-container>

</v-content>
<v-footer fixed="fixed" color="blue darken-3" app>
    <div>Tous Les droit reserver &copy; {{ new Date().getFullYear() }}</div>
</v-footer>

</v-app>
</template>
<script type="text/javascript">
import Footer from '~/components/Footer.vue'
export default {
  components: {
    Footer
  },
  data () {
    return {
      clipped: false,
      drawer: false,
      right: null,
      items: [
        { icon: 'dashboard', text: 'Tableau de Bord' },
        { icon: 'history', text: 'Consomation' },
        {
          icon: 'keyboard_arrow_up',
          'icon-alt': 'keyboard_arrow_down',
          text: 'Type d inergie',
          model: false,
          children: [
            { icon: 'event', text: 'Electricité' },
            { icon: 'home', text: 'Gaz' },
            { icon: 'map', text: 'Eaux' },
            { icon: 'icon-alt', text: 'Internet' },
            { icon: 'business', text: 'Autre' }
          ]
        },
        { icon: 'settings', text: 'Parrametre' },
        { icon: 'help', text: 'Help' },
        { icon: 'keyboard', text: 'Nous contacter' }
      ]
    }
  }

}
</script>
