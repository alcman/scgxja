<template>
  <div>
    <div class="b1">
      <button type="button1" class="sendMessage">
        <img src="../static/xinxi_icon.png" />
        <span class="s1">信息报送</span>
      </button>
    </div>
    <div class="b2">
      <button type="button2" class="laws">
        <img src="../static/zixun_icon.png" />
        <span class="s2">法律咨询</span>
      </button>
    </div>
    <div class="b3">
      <button type="button3" class="affairs">
        <img src="../static/yewu_icon.png" />
        <span class="s3">业务工作</span>
      </button>
    </div>
    <div class="b4">
      <button type="button4" class="organ">
        <img src="../static/yewu_icon.png" />
        <span class="s4">机构公开</span>
      </button>
    </div>
  </div>
</template>
<script>
export default {
    name:"Buttons"
}
</script>
<style lang="scss" scoped>
.sendMessage {
  width: 327px;
  height: 102px;
  background-color: royalblue;
}

.laws {
  width: 327px;
  height: 102px;
  background-color: yellow;
}

.affairs {
  width: 327px;
  height: 102px;
  background-color: green;
}

.organ {
  width: 327px;
  height: 102px;
  background-color: red;
}

img {
  vertical-align: middle;
  display: inline-block;
}

.s1 {
  color: white;
  font-size: 30px;
}

.s2 {
  color: white;
  font-size: 30px;
}

.s3 {
  color: white;
  font-size: 30px;
}

.s4 {
  color: white;
  font-size: 30px;
}

.b2 {
  margin-top: 10px;
}
.b3 {
  margin-top: 10px;
}
.b4 {
  margin-top: 10px;
}
button{
  border: none;
}
</style>