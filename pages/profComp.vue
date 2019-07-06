<template>
<div>
    <toolbar />
<h3 class="text-xs-center my-4">SNS連携をする事で<br />このアプリの機能を全て使えます。</h3>
 <!-- <div>twitter user id: {{ user.id }}</div>
    <div>error: {{ error }}</div> -->
        <v-btn id="btnView" color="#1DCD00">
            Lineを連携させる
        </v-btn>
        
          <v-btn color="#3DCDEF" href="http://127.0.0.1:3000/server/auth/twitter">
            Twitterを連携させる
        </v-btn>
         <v-container id="card" >
         <h3 class="text-xs-center my-4">利用規約</h3>
             <v-card class="card" color="purple" dark 
             style="width: 80vw;  margin: 0 25px;"
             >
              <v-card-text>この利用規約（以下，「本規約」といいます。）は，＿＿＿＿＿（以下，「当社」といいます。）がこのウェブサイト上で提供するサービス（以下，「本サービス」といいます。）の利用条件を定めるものです。登録ユーザーの皆さま（以下，「ユーザー」といいます。）には，本規約に従って，本サービスをご利用いただきます。</v-card-text>
         </v-card>
       
        </v-container>
   <div class="text-xs-center">
    <v-btn round color="orange">登録完了</v-btn>
  </div>
</div>
</template>

<script>
import toolbar from '~/components/toolbar.vue'
import axios from 'axios';
export default {
    data() {
    return {
      user: {},
      error: null,
    };
  },
   components: {
        toolbar
    },
mounted() {
    // 1
    axios.get('http://127.0.0.1:3000/server/auth/twitter/callback', {
      params: this.$route.query,
    }).then(res => {
      // 3
      this.user = res.data.user;
    //   axios.post('https://api.twitter.com/1.1/statuses/update.json', {
    //      status: 'テスト',
    //   });
    // //   axios.post(Helper.getUserAPI(),{
    // //     headers: {
    // //                 'Content-Type': 'application/json',
    // //                 'Authorization':res.oauth_token
    // //     },
    // //   })
    //   console.log(res.oauth_token);
      //authToken取得
    }).catch(err => {
      this.error = err;
    });
  },
}
</script>

<style scope>
  #btnView {
       margin-bottom: 32px;
  }
  #card {
margin-bottom: 32px;
  }
</style>
