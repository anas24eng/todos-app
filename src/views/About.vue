<template>
  <div class="about pa-8">
    <h1>WELCOME TO ABOUT PAGE <br>
      </h1>
      <h4>This page to show litile info about Todos</h4>
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Necessitatibus eius harum quae maxime numquam distinctio minus autem! Quos, repellendus eligendi, porro quisquam possimus qui perferendis eveniet nulla harum alias iste.</p>
       <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Necessitatibus eius harum quae maxime numquam distinctio minus autem! Quos, repellendus eligendi, porro quisquam possimus qui perferendis eveniet nulla harum alias iste.</p>
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Necessitatibus eius harum quae maxime numquam distinctio minus autem! Quos, repellendus eligendi, porro quisquam possimus qui perferendis eveniet nulla harum alias iste.</p>
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Necessitatibus eius harum quae maxime numquam distinctio minus autem! Quos, repellendus eligendi, porro quisquam possimus qui perferendis eveniet nulla harum alias iste.</p>
  <v-sheet
    :color="`grey ${theme.isDark ? 'darken-2' : 'lighten-4'}`"
    class="pa-3"
  >
    <v-skeleton-loader
      class="mx-auto"
      max-width="300"
      type="card"
    ></v-skeleton-loader>
  </v-sheet>
  </div>
</template>
<script>
  export default {
    // Vuetify components provide
    // a theme variable that is
    // used to determine dark
    inject: {
      theme: {
        default: { isDark: false },
      },
    },
  }
</script>

