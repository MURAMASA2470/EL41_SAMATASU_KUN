<template>
<ol class="stepBar">
<li class="visited"></li>
<li></li>
<li></li>
<li></li>
</ol>
</template>
<script>
  export default {
    data () {
      return {
        e1: 0
      }
    }
  }
</script>
<style scoped>
.stepBar {
  display: flex;
  position: relative;
  margin: 20px auto;
  text-align: center;
}
.stepBar li {
  font-size: 12px;
  list-style: none;
  position: relative;
  width: 30%;
}
.stepBar li:after {
  background: #EB8712;
  content: "";
  width: calc(100% - 24px);
  height: 4px;
  position: absolute;
  left: calc(-50% + 12px);
  top: 10px;
}
.stepBar li:first-child:after {
  display: none;
}
.stepBar li span {
  background: #EB8712;
  color: #ffffff;
  display: inline-block;
  height: 24px;
  margin-bottom: 5px;
  line-height: 24px;
  width: 24px;
  -moz-border-radius: 50%;
  -webkit-border-radius: 50%;
  border-radius: 50%;
}
.stepBar .visited:after {
  background: #EB8712;
}
.stepBar .visited span {
  background:#EB8712;
}

</style>
