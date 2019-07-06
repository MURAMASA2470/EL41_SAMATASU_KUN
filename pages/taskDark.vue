<template　id="app">
    <div>
        
        <div>
            <h3 class="text-xs-center my-4">宿題一覧</h3>

            <v-sheet class="work-item" v-for="(subject, i) in x['教科']" :key="i" color="black">
                
                    <label class="work-content">{{ subject['名前'] }} の {{ x['種類'][i]['名前'] }}</label>
                    <label class="work-amount">{{5+i}}{{ x['種類'][i]['単位'] }}</label>
                
            </v-sheet>

        </div>

        <div class="next-btn">
            <v-btn  href="/submitTask" color="#EB8712" round>
                課題を提出する
            </v-btn>
        </div>

        
    </div>
</template>

<style  >

    * {
        color: red;
        
    }

    .__nuxt {
                background-color: black !important;

    }

    .__layout {
                background-color: black !important;

    }

    .v-content__wrap {
        background-color: black !important;
    }

    .application--wrap {
                background-color: black !important;

    }

    .v-content {
                        background-color: black !important;

    }

   #app5 {
                        background-color:black !important;

    }

   
    .next-btn .v-btn{
        border: solid 2px red !important;
        background-color: rgba(0, 0, 0, 0.8) !important;
        color: white;
    }

    .v-dialog .v-btn {
        width: 100%;
        margin: 40px 0;
    }

        .card-body {
            padding-top: 30px;
        }

            .dialog-text {
                padding: 10px 0;
                font-size: 1.2rem;
            }

    .next-btn {
        position: absolute;
        bottom: 35px;
    }    

    .work-item {
        height: 60px;
        border-radius: 10px;
        margin: 25px 30px;
        font-size: 1.5rem;
        padding: 5px 10px;
        position: relative;
        background-color: black;
        border: solid 2px white !important;
    }

        .work-content {
            position: absolute;
            text-align: left;
            left: 15px;
            top: 25%;
        }

        .work-amount {
            position: absolute;
            text-align: right;
            right: 45px;
            top: 25%;
        }
</style>

<script>
import setting from "../config/samatasu.json"

console.log(setting['教科'][0]['色']);

export default {
    data: () => {
        return {
            dialog: false,
            x: setting, 
            subjectList: setting['教科'].map((x) => {
                return x['名前'];
            }), 
            genreList : setting['種類'].map((x) => {
                return x['名前'];
            }), 
            amountList: [...Array(99).keys()].map(i => ++i)
            
        }
    }, 
    created: () => {
     
    }
}
</script>
