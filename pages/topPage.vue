<template>
<div>
<h1 class="text-xs-center my-4">サマタスくんを始める</h1>
        <v-btn color="#EB8712">
            新規登録
        </v-btn>

        <a class="cancel" href="http://localhost:3000/profComp">キャンセル</a>

</div>
</template>

<script>
export default {

}
</script>

<style scope>

.v-btn {
   margin-bottom: 32px;
   border-radius: 100px;
  }
.v-content__wrap{
  background-color: #6ADDFF;
}
h1{
  padding: 200px 0;
  color:#FFFFFF;
}
.border{
  border: solid 2px #FFFFFF;
  width: 75vw;
  margin: 0 auto 20px auto;

}
.cancel:link{
  color:white;
  text-decoration:none;
}
.cancel:visited{
  color:white;
}
.cancel:hover{
  color:white;
}
.cancel:active{
  color:white;
}
.cancel{
  display: block;
  width: 100px;
  margin: 0 auto;
  text-align: center;
}
</style>
