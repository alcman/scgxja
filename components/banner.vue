<template>
  <div>
    <transition-group tag="ul" name="slide">
      <li
        v-for="(value,index) in list"
        :key="index"
        v-show="index===currentIndex"
        @mouseenter="stop"
        @mouseleave="go"
      >
        <img class="imgs" :src="value.path" />
      </li>
    </transition-group>
    <div class="carousel-items">
      <span
        v-for="(item,index) in list.length"
        :class="{'active':index===currentIndex}"
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
      timer: ""
    };
  },
  methods: {
    autoPlay() {
      setTimeout(() => {
        this.currentIndex++;
        if (this.currentIndex > this.list.length - 1) {
          this.currentIndex = 0;
        }
      }, 2000);
    },

    // autoPlay() {
    //   this.currentIndex++;
    //   if (this.currentIndex > this.list.length - 1) {
    //     this.currentIndex = 0;
    //   }
    // },
    go() {
      this.timer = setInterval(() => {
        this.autoPlay();
      }, 4000);
    },
    stop() {
      clearInterval(this.timer);
      this.timer = null;
    },
    change(index) {
      this.currentIndex = index;
    }
  },
  created() {
    this.$nextTick(() => {
      this.timer = setInterval(() => {
        this.autoPlay();
      }, 4000);
    });
  }
};
</script>

<style lang="scss" scoped>
.imgs {
  width: 1150px;
  height: 360px;
}
ul {
  list-style: none;
  padding: 0;
  white-space: nowrap;
  li {
    display: inline-block;
    width: 100%;
    height: 100%;
    vertical-align: top;
  }
}
.slide-enter-to {
  transition: all 1s ease;
  transform: translateX(0);
}

.slide-leave-active {
  transition: all 1s ease;
  transform: translateX(-100%);
}

.slide-enter {
  transform: translateX(100%);
}

.slide-leave {
  transform: translateX(0);
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
    border-radius:10px;
    margin: 0 3px;
    background-color: #b2b2b2;
    cursor: pointer;
  }
  .active {
    background-color: blue;
  }
}
</style>