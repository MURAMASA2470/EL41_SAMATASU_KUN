<template>
<div>
    <toolbar  />
  
    <v-container>
      <v-layout>
         <v-flex xs6 sm6 md3>
             <p>苗字</p>
          <v-text-field
           solo
          ></v-text-field>
        </v-flex>
        <v-flex xs6 sm6 md3>
           <p>名前</p>
          <v-text-field
           solo
          ></v-text-field>
        </v-flex>
      </v-layout>
    </v-container>
     <v-container>
      <v-layout>
         <v-flex xs12 sm6 md3>
           <p>学校名</p>
          <v-text-field
          solo
          ></v-text-field>
        </v-flex>
        </v-layout>
     </v-container>
     <v-container>
      <v-layout>
        <v-flex xs12 sm6 d-flex>
            <v-select
              :items="items"
            solo
            ></v-select>
         </v-flex>
        </v-layout>
    </v-container>
     <div class="text-xs-center">
    <v-btn round color="orange">次へ</v-btn>
  </div>
</div>
</template>
<script>
import toolbar from '~/components/toolbar.vue'
export default {
   data: () => ({
      items: ['1年', '2年', '3年', '4年', '5年', '6年']
    }),
components: {  
   toolbar
  }
}
</script>
