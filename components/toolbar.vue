<template>
    <v-toolbar
      fixed
      app
    >

      <v-btn
        icon
         v-if="back"
        :to="backLink"
      >
        <v-icon>arrow_back_ios</v-icon>
      </v-btn>
       <v-spacer></v-spacer>  
     <v-btn icon to="/search" v-if="searchIcon" >
        <v-icon >search</v-icon>
      </v-btn>
      
    </v-toolbar>
</template>
<script>
export default {
  props:['searchIcon','back','backLink']
}
</script>
