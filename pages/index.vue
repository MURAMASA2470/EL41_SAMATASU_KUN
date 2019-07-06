<template>
<div>
  
<h1 class="text-xs-center my-4">Line,Twitter<br>連携画面</h1>
        <v-btn to="profInput" color="#1DCD00" class="get-bu">
            新規登録
        </v-btn>
        <hr class="border">

        <v-btn color="#1DCD00" class="sns-bu">
            Lineを連携させる
        </v-btn>
        
        <v-btn color="#3DCDEF" class="sns-bu">
            Twitterを連携させる
        </v-btn>
</div>
</template>

<script>
export default {

}
</script>

<style scoped>

.v-btn {
   margin-bottom: 32px;
   border-radius: 100px;
  }
.v-content__wrap{
  background-color: #6ADDFF;
}
h1{
  padding: 180px 0;
  color:#FFFFFF;
}
.border{
  border: solid 2px #FFFFFF;
  width: 75vw;
  margin: 0 auto 20px auto;

}
.get-bu{
  border-radius: 5px;
}
.sns-bu{
  border-radius: 100px;
}
</style>
