<template>
<div>
    <!-- <toolbar /> -->
    <h3 class="text-xs-center my-4" style="color:red;">宿題を選択</h3>
    <v-container style="width: 80vw;">
     <v-flex xs12 sm6 d-flex>
            <v-select
              :items="items"
            solo
            ></v-select>
         </v-flex>
     </v-container>
       <h3 class="text-xs-center my-4"  style="color:red;">課題をアップロード</h3>
    <v-container style="width: 80vw;">
     <v-flex xs12 sm6 md3>
          <v-text-field
          solo
           label="課題を提出"
          type="file"
          class="file"
          ></v-text-field>
        </v-flex>
     </v-container>
      <v-progress-circular
      :rotate="360"
      :size="100"
      :width="15"
      :value="value"
      color="orange"
     id="progress"
    >
      {{ value }}
    </v-progress-circular>
   
        <div class="text-xs-center next-btn" style="margin-top:200px;">
            <v-btn @click="progress" round color="orange">課題を提出</v-btn>
        </div>
</div>
</template>
<script>
import toolbar from '~/components/toolbar.vue'
export default {
    data: () => ({
      items: ['国語の宿題', '算数の宿題', '理科の宿題', '社会の宿題', '英語の宿題'],
      interval: {},
        value: 0
    }),
     beforeDestroy () {
      clearInterval(this.interval)
    },
    components:{
        toolbar
    },methods: {
        progress : function (){
            document.getElementById("progress").style.display = "block";
             this.interval = setInterval(() => {
     
          if (this.value === 100) {
               document.getElementById("progress").style.display = "none";
             return (this.value = 0)
          }
        this.value += 10
      }, 1000)

        }
    }

}
</script>
<style scope>
#progress{
    display: none;
    margin-left:150px;

}

.v-content__wrap {
        background-color: black !important;
    }

.next-btn .v-btn{
        border: solid 2px red !important;
        background-color: rgba(0, 0, 0, 0.8) !important;
        color: white;
    }
</style>

