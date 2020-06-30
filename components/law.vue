<template>
  <div>
    <div class="inner" id="inner">
      <span class="title">政策法规</span>
      <a href="\">
        <span class="more">更多>></span>
      </a>
    </div>
    <div class="list">
      <span>
        <ul>
          <li v-for="(site,index) in sites" v-bind:key="index">
            <a href="\">{{site.law}}</a>
            <span class="date">2020-6-30</span>
          </li>
        </ul>
      </span>
    </div>
  </div>
</template>  

    <script>
export default {
  name: "Law",
  data() {
    return {
      sites: [
        { law: "绵阳市安州区" },
        { law: "绵阳市安州区" },
        { law: "绵阳市安州区" },
        { law: "绵阳市安州区" }
      ]
    };
  }
};
</script>
    
   <style lang="scss" scoped>
.inner {
  width: 387px;
  height: 40px;
  background-color: red;
  line-height: 40px;
}

.more {
  float: right;
}
.title {
  color: white;
}
.more {
  text-decoration: none;
  color: white;
}
a {
  text-decoration: none;
}
ul {
  line-height: 40px;
}
.date{
  float: right;
}
</style>