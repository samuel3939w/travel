<template>
  <div class="icons">
    <swiper :options="swiperOption">
      <swiper-slide v-for="(page, index) of pages" :key="index">
        <div class="icon" v-for="item of page" :key="item.id">
          <div class="icon-img">
            <img class="icon-img-content" :src="item.imgUrl" />
          </div>
          <p class="icon-desc">{{ item.desc }}</p>
        </div>
      </swiper-slide>
    </swiper>
  </div>
</template>

<script>
export default {
  name: "HomeIcons",
  props:{
    list:Array
  },
  data(){
    return{
      swiperOption:{
        autoplay:false
      }
    }
  },
  computed: {
    pages() {
      const pages = [];
      this.list.forEach((item, index) => {
        const page = Math.floor(index / 8);
        if (!pages[page]) {
          pages[page] = [];
        }
        pages[page].push(item);
      });
      return pages;
    },
  },
};
</script>

<style lang="scss" scoped>
@import "~styles/varibles.scss";
@import "~styles/mixins.scss";

// .icons {
//   overflow: hidden;
//   width: 100%;
//   height: 0;
//   // 撑开的宽度是父元素宽度的50%，父元素为body，也就是100%。其实也就是页面宽度的一半
//   padding-bottom: 50%;
//   background-color: pink;

//   .icon {
//     float: left;
//     width: 25%;
//     height: 0;
//     // 撑开的高度是父元素宽度的25%，父元素为icons，其宽度为100%。其实也就是页面宽度的25%
//     padding-bottom: 25%;
//     background-color: green;
//     display: flex;
//     align-items: center;
//     flex-direction: column;

//     .icon-img {
//       width: 50%;
//       height: 0;
//       padding-bottom: 50%;
//       overflow: hidden;
//       margin: 0.2rem 0;

//       img {
//         width: 100%;
//       }
//     }

//     .icon-desc {
//       color: $darkTextColor;
//     }
//   }
// }

.icons >>> .swiper-slide {
  height: 0;
  padding-bottom: 50%;
}
.icons {
  margin-top: 0.1rem;
  .icon {
    position: relative;
    overflow: hidden;
    float: left;
    height: 0;
    width: 25%;
    padding-bottom: 25%;
    &-img {
      position: absolute;
      top: 0;
      right: 0;
      left: 0;
      bottom: 0.44rem;
      box-sizing: border-box;
      padding: 0.1rem;
      &-content {
        display: block;
        margin: 0 auto;
        height: 100%;
      }
    }
    &-desc {
      position: absolute;
      left: 0;
      right: 0;
      bottom: 0;
      height: 0.44rem;
      line-height: 0.44rem;
      text-align: center;
      color: $darkTextColor;
      @include ellipsis;
    }
  }
}
</style>
