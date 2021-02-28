<template>
  <v-app id="inspire">
     <v-navigation-drawer 
     v-model="drawer"
     app>
     
   
      <v-list-item>
        
         
          <v-avatar>
      <img
        src="https://cdn.vuetifyjs.com/images/john.jpg"
        alt="John"
      >
    </v-avatar>
        <v-list-item-content>
          <v-list-item-title class="title">
            Todos
          </v-list-item-title>
          <v-list-item-subtitle>
            Best Todo
          </v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>

      <v-divider></v-divider>

      <v-list
        dense
        nav
      >
     
     
  
        <v-list-item
          v-for="item in items"
          :key="item.title"
          :to="item.to"
          link
        >
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

   <v-app-bar
    app 
      color= "primary"
      dark
      src="https://picsum.photos/1920/1080?random"
      prominent
    >
    
      <template v-slot:img="{ props }">
        <v-img
          v-bind="props"
          gradient="to top right, rgba(19,84,122,.5), rgba(128,208,199,.8)"
        ></v-img>
      </template>
     

      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>

      <v-toolbar-title>Today Tasks</v-toolbar-title>

      <v-spacer></v-spacer>

      <v-btn icon>
        <v-icon>mdi-magnify</v-icon>
      </v-btn>

      <v-btn icon>
        <v-icon>mdi-heart</v-icon>
      </v-btn>

      <v-btn icon>
        <v-icon>mdi-dots-vertical</v-icon>
      </v-btn>
    </v-app-bar>

    <v-main>
    <router-view></router-view>
    </v-main>
     <v-footer 
     app
     shaped
     outlined
    color="primary lighten-1"
    padless
  >
    <v-row
      justify="center"
      no-gutters
    >
      <v-btn
        v-for="link in links"
        :key="link"
        color="white"
        text
        rounded
        class="my-2"
        :to="link.to"
        

      >
     
        {{ link }}
      </v-btn>
      <v-col
        class="primary lighten-2 py-4 text-center white--text"
        cols="12"
      >
        {{ new Date().getFullYear() }} — <strong>Todos</strong>
      </v-col>
    </v-row>
  </v-footer>
  </v-app>
</template>

<script>
  export default {
    data: () => ({drawer: null,
    links: [
        'Home', 
        'About Us',
        'Login'
      ],
  
    
     items: [
          { title: 'Login', icon: 'mdi-login', to:'login' },
          { title: 'Todos', icon: 'mdi-check-all', to: '/' },
          { title: 'About', icon: 'mdi-help-box', to:'about' },

        ],}),
       

  }
</script>