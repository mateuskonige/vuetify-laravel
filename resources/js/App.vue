<template>
<v-app>
  <v-navigation-drawer app v-model="drawer">
    <nav-component></nav-component>
  </v-navigation-drawer>

  <v-app-bar app elevation="1">
    
      <v-app-bar-nav-icon @click="toggle()"></v-app-bar-nav-icon>

      <v-toolbar-title>Clientes</v-toolbar-title>
  </v-app-bar>

  <!-- Sizes your content based upon application components -->
  <v-main>

    <!-- Provides the application the proper gutter -->
    <v-container fluid>
    <v-breadcrumbs :items="items" ></v-breadcrumbs>
  <v-data-table 
    
    :headers="headers"
    :items="desserts"
    :items-per-page="5"
    class="elevation-1"
  ></v-data-table>


      <!-- If using vue-router -->
      <router-view></router-view>      
    </v-container>
  </v-main>

  <v-footer app>  
    
  </v-footer>
</v-app>
</template>

<script>
export default {
  name: "App",
  data() {
     return {
        dialog: false,
      items: [
        {
          text: 'Dashboard',
          disabled: false,
          href: 'breadcrumbs_dashboard',
        },
        {
          text: 'Link 1',
          disabled: false,
          href: 'breadcrumbs_link_1',
        },
        {
          text: 'Link 2',
          disabled: true,
          href: 'breadcrumbs_link_2',
        },
      ],
      items2: [
          { icon: 'mdi-clipboard-text', iconClass: 'blue white--text', title: 'Vacation itinerary', subtitle: 'Jan 20, 2014' },
          { icon: 'mdi-gesture-tap-button', iconClass: 'amber white--text', title: 'Kitchen remodel', subtitle: 'Jan 10, 2014' },
        ],
      }
    },
      data: () => ({
      drawer: false,
      group: null,
    }),
    methods: {
      toggle() {
        if (this.drawer == true) {
          this.drawer = false
        } else {
          this.drawer = true
        }
      }
    }
  }

</script>