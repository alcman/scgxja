<template>
  <div class="wrapper">
    <ul
      :style="{ transform: `translate3d(-${transX}, 0, 0)` }"
      :class="{ animation: isAnimation }"
      @mouseenter="stop"
      @mouseleave="go"
    >
      <li v-for="value in imgList" :key="value.pic">
        <img class="imgs" :src="value.path" />
      </li>
    </ul>
    <div class="carousel-items">
      <span
        v-for="(item, index) in list.length"
        :class="{ active: index === carouselIndex }"
        :key="index"
        @mouseover="change(index)"
      ></span>
    </div>
  </div>
</template>

<script>
export default {
  name: "Banner",
  data() {
    return {
      list: [
        {
          pic: "banner1",
          path: "/banner.jpg"
        },
        // {
        // pic:"banner1",
        //   path: "/banner.jpg"
        // },
        {
          pic: "banner2",
          path: "/logo.png"
        }
      ],
      currentIndex: 0,
      isAnimation: true,
      timer: ""
    };
  },
  computed: {
    imgList() {
      if (this.list.length) {
        return this.list.concat(this.list[0]);
      }
      return [];
    },
    transX() {
      return `${parseInt(this.currentIndex) * 100}%`;
    },
    carouselIndex() {
      if (this.currentIndex === this.list.length) return 0;
      return this.currentIndex;
    }
  },
  methods: {
    autoPlay() {
      this.timer = setInterval(() => {
        this.currentIndex++;
        if (this.currentIndex >= this.list.length) {
          setTimeout(() => {
            // 取消动画效果
            this.isAnimation = false;
            // 无动画切换到第0张
            this.currentIndex = 0;
            // 打开动画效果，使用setTimeout防止动画立即生效
            setTimeout(() => {
              this.isAnimation = true;
            }, 200);
          }, 800);
        }
      }, 4000);
    },
    go() {
      this.autoPlay();
    },
    stop() {
      clearInterval(this.timer);
      this.timer = null;
    },
    change(index) {
      this.currentIndex = index;
    }
  },
  mounted() {
    this.autoPlay();
  }
};
</script>

<style lang="scss" scoped>
.wrapper {
  overflow: hidden;
}
.imgs {
  width: 1150px;
  height: 360px;
}
ul {
  padding: 0;
  font-size: 0;
  white-space: nowrap;
  &.animation {
    transition-duration: 0.35s;
  }
  li {
    display: inline-block;
    list-style: none;
    width: 100%;
    height: 100%;
    vertical-align: top;
  }
}
.carousel-items {
  z-index: 10;
  top: 380px;
  width: 100%;
  margin: 0 auto;
  text-align: center;
  font-size: 0;
  span {
    display: inline-block;
    height: 10px;
    width: 10px;
    border-radius: 10px;
    margin: 0 3px;
    background-color: #b2b2b2;
    cursor: pointer;
  }
  .active {
    background-color: blue;
  }
}
</style>
