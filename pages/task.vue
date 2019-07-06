<template>
    <div>
        <h3 class="text-xs-center my-4">夏休みの宿題を登録してください</h3>

        <v-dialog v-model="dialog" width="500">
            <template v-slot:activator="{ on }">
                <v-btn color="#1DCD00" v-on="on">
                    <v-icon>add</v-icon>
                    宿題の追加
                </v-btn>
            </template>

            <v-card>

                <v-card-title class="headline grey lighten-2" primary-title>
                    宿題の追加
                </v-card-title>

                <div class="card-body">

                    <v-layout row class="">

                        <v-flex xs4 py-3 text-xs-center>
                            <label class="dialog-text">名前</label>
                        </v-flex>

                         <v-flex xs8 d-flex px-3>                    
                            <v-text-field
                                solo
                            ></v-text-field>
                        </v-flex>

                    </v-layout>

                    <v-layout row class="">

                        <v-flex xs4 py-3 text-xs-center>
                            <label class="dialog-text">教科</label>
                        </v-flex>

                         <v-flex xs8 d-flex px-3>
                            <v-select
                            :items="items"
                            solo
                            ></v-select>
                        </v-flex>

                    </v-layout>

                    <v-layout row class="">

                        <v-flex xs4 py-3 text-xs-center>
                            <label class="dialog-text">種類</label>
                        </v-flex>

                         <v-flex xs8 d-flex px-3>
                            <v-select
                            :items="items"
                            solo
                            ></v-select>
                        </v-flex>

                    </v-layout>

                    <v-layout row class="">

                        <v-flex xs4 py-3 text-xs-center>
                            <label class="dialog-text">量</label>
                        </v-flex>

                         <v-flex xs8 d-flex px-3>
                            <v-select
                            :items="items"
                            solo
                            ></v-select>
                        </v-flex>

                    </v-layout>

                </div>

                <!-- <v-divider></v-divider> -->

                <v-card-actions>
                        
                    <v-btn color="#EB8712" @click="dialog = false">
                        追加する
                    </v-btn>

                </v-card-actions>

            </v-card>
        </v-dialog>

        <div>
            <h3 class="text-xs-center my-4">宿題一覧</h3>

            <v-sheet class="work-item" v-for="n in 6" :key="n" color="#ADFF57">
                
                    <label class="work-content">{{ subject }} の {{ category }}</label>
                    <label class="work-amount">{{ workAmount }}</label>
                
            </v-sheet>

        </div>

        <div class="next-btn">
            <v-btn color="#EB8712" round>
                次へ
            </v-btn>
        </div>

        
    </div>
</template>

<style scoped>
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
export default {
    data: () => {
        return {
            dialog: false,

        }
    }
}
</script>
