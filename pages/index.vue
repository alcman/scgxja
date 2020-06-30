<template>
  <div class="container">
    <div class="header">
      <span class="logo">
        <img src="../static/logo.png" />
      </span>
      <div class="login">
        <a href="\" class="a1">
          <span>
            <img src="../static/msg_icon.png" />
            消息
          </span>
        </a>
        <a href="\" class="a2">
          <span>
            <img src="../static/msg_icon.png" />
            登录
          </span>
        </a>
      </div>
    </div>
    <div class="main">
      <!-- <div class="header">
        <span class="title">
          <img src="../static/logo.png" />
        </span>
      </div>-->
      <div class="banner">
        <!-- <img src="../static/banner.jpg" /> -->
        <Banner></Banner>
      </div>
      <div class="views">
        <div class="law">
          <Law></Law>
        </div>
        <div class="product">
          <Product></Product>
        </div>
        <div class="buttons">
          <Buttons></Buttons>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import Law from "@/components/law.vue";
import Buttons from "@/components/buttons.vue";
import Product from "@/components/product.vue"
import Banner from "@/components/banner.vue"
export default {
  components: {
    Law,
    Buttons,
    Product,
    Banner
  }
};
</script>

<style>
.container {
  background-image: url(../static/bg.jpg);
  height: 965px;
}
.main {
  width: 1200px;
  height: 830px;
  margin: 0 auto;
  background-color: white;
  overflow: hidden;
}
.header {
  width: 1200px;
  height: 131px;
  margin: 0 auto;
}
.logo {
  margin-top: 30px;
  display: inline-block;
}
.login {
  float: right;
  margin-top: 65px;
}
.banner {
  height: 360px;
  margin: 0 25px;
  margin-top: 15px;
}
.views {
  height: 406px;
  background-color: white;
  margin: 0 25px;
}
.law {
  width: 387px;
  height: 400px;
  float: left;
  margin-top: 15px;
}
.product {
  width: 387px;
  height: 400px;
  float: left;
  margin-top: 15px;
  margin-left: 25px;
}
.buttons {
  width: 327px;
  height: 400px;
  float: right;
  margin-top: 15px;
}
.a1 {
  text-decoration: none;
  color: white;
}
.a2 {
  text-decoration: none;
  color: white;
}
</style>
