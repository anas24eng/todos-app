<template>
  <v-app>
    <v-card width="400" class="mx-auto mt-5" >
      <v-card-title>
        <h1 class="display-1">Login</h1>
      </v-card-title>
      <v-card-text>
        <v-form>
          <v-text-field label="Username" append-icon="mdi-account-circle" />
          <v-text-field  :type="showPassword ?
           'text' : 'password' "
           label="Password" 
            prepend-icon="mdi-lock"
           :append-icon="shwoPassword ? 'mdi-eye' :
           'mdi-eye-off'" 
          @click:append="showPassword = ! showPassword"
           />
         
        </v-form>
      </v-card-text>
      <v-card-actions>
        <v-btn color="success"> Register </v-btn>
        <v-spacer></v-spacer>
        <v-btn color="info"> Login </v-btn>
      </v-card-actions>
    </v-card>
  <v-parallax src="https://cdn.vuetifyjs.com/images/parallax/material.jpg"></v-parallax>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      showPassword: false
    }
  },
}
</script>