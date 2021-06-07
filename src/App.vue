<template>
  <div id="app">
    <!-- App.vue -->
    <v-app>
      <!--<v-navigation-drawer app>
      
      </v-navigation-drawer>-->
    
      <v-app-bar color="primary" app dark="dark">
        <v-toolbar-title >Fek Translate</v-toolbar-title>
      </v-app-bar>
    
      <!-- Sizes your content based upon application components -->
      <v-main>
      
        <!-- Provides the application the proper gutter -->
        <v-container fluid>
        
          <!-- If using vue-router -->
          <router-view></router-view>
        </v-container>
      </v-main>
    
      <v-footer app>
        <!-- -->
      </v-footer>
    </v-app>

  </div>
</template>

<style lang="scss">

</style>
