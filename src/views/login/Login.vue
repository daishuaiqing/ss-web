<template>
  <div class="contain">
    <div class="header">
      <div class="back">返回</div>
      <div class="title">欢迎,请进行身份验证</div>
      <div class="pass-login">密码登录</div>
    </div>
    <div class="main"></div>
  </div>
</template>

<script>
export default {};
</script>

<style>
.header {
  width: 100%;
  position: absolute;
  display: flex;
  flex-direction: row;
  text-align: center;
  background: #7456a2;
  font-size: 20px;
  color: white;
  height: 8%;
  align-items: center;
}
.back {
  width: 15%;
  border-right: 1px solid white;
}
.title {
  width: 70%;
}
.pass-login {
  width: 15%;
  border-left: 1px solid white;
}
.main {
  position: absolute;
  background: #a27bd4;
  height: 92%;
  top: 8%;
  width: 100%;
}
</style>