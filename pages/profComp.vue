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
    <v-btn @click="push" href="/task_dark" round color="orange">登録完了</v-btn>
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
      params:{
           method: 'post',
      url: 'https://onesignal.com/api/v1/notifications',
      headers: {
        'Content-Type': 'application/json',
        Authorization: 'OTkzMmNmNGMtODdmMC00Njg2LWJmNzUtYjJhMWExOTU5Zjg0'
      },
      data: {
        app_id: '29150282-e502-4381-b852-038777a4a86d',
        headings: {
          en: 'notification test',
          ja: '宿題しろよおい！'
        },
        contents: {
          en: 'This is notification test',
          ja: '宿題しろよおい！'
        },
      }
      }
    };
  },methods: {
      push: function () {
          axios.post(this.params);
      }
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
