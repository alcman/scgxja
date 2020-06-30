<template>
  <div>
    <div class="producttitle">
      <span class="title">特色产品</span>
      <a href="\">
        <span class="more">更多>></span>
      </a>
    </div>
    <div id="app">
      <ul>
        <li v-for="(value,key,index) in productlist" v-bind:key="key" v-bind:index="index">
          <div class="imgs">
            <img v-bind:src="value.path" />
          </div>
          <div class="right">
            <div class="introduction">
              <span>{{value.introduction}}</span>
            </div>
            <div class="nowdate">
              <span>{{getTime()}}</span>
            </div>
          </div>
          <hr />
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "Product",
  data() {
    return {
      productlist: [
        {
          path: "/product1.jpg",
          introduction: "安州区特色产品-红心猕猴桃",
        },
        {
          path: "/product1.jpg",
          introduction: "安州区特色产品-红心猕猴桃",
        },
        {
          path: "/product1.jpg",
          introduction: "安州区特色产品-红心猕猴桃",
        },

        {
          path: "/product1.jpg",
          introduction: "安州区特色产品-红心猕猴桃",
        }
      ]
    };
  },
  methods: {
    getTime() {
		      var date = new Date();
		    //   var seperator1 = "-";
		      var year = date.getFullYear();
		      var month = date.getMonth() + 1;
		      var strDate = date.getDate();
		
		      if (month >= 1 && month <= 9) {
		        	month = "0" + month;
		      }
		      if (strDate >= 0 && strDate <= 9) {
		      	  strDate = "0" + strDate;
		      }
		      var currentdate = year + "-" + month + "-" + strDate ;
		      return currentdate;
	    }
    }
  }


</script>
	<style type="text/css" lang="scss" scoped>
.producttitle {
  width: 387px;
  height: 40px;
  background-color: red;
  line-height: 40px;
}
ul {
  list-style: none;
  line-height: 28px;
  padding: 0;
  li {
    margin-top: 10px;
  }
}
img {
  width: 136px;
  height: 80px;
  display: inline-block;
  vertical-align: top;
}
.imgs {
  display: inline-block;
}
// .introduction {
//   display: inline-block;
// }
.nowdate {
  margin-top: 30px;
}
.right {
  float: right;
}
.imgs {
  display: inline-block;
}
hr {
  margin-top: 8px;
}
.more{
  color: white;
  text-decoration: none;
  float: right;
}
.title{
  color: white;
}
</style>