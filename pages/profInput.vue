<template>
<div>
    <toolbar leftBtn=true  />
    <!-- <stepper /> -->
    <v-container>
      <v-layout >
         <v-flex xs6 sm6 md3  style="padding-right:10px;">
             <p>苗字</p>
          <v-text-field
           solo
           pr4
          ></v-text-field>
        </v-flex>
        <v-flex xs6 sm6 md3 style="padding-left:10px;">
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
          <p>学年</p>
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
    <v-btn  href="/task" round color="orange">次へ</v-btn>
  </div>
</div>
</template>
<script>
import toolbar from '~/components/toolbar.vue'
import stepper from '~/components/stepper.vue'
export default {
   data: () => ({
      items: ['1年', '2年', '3年', '4年', '5年', '6年'],
    }),
    components: {  
        toolbar,
        stepper
  }
}
</script>
