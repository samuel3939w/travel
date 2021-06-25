<template>
  <div class="container" @click="handleGallaryClick">
    <div class="wrapper">
      <swiper :options="swiperOption">
        <swiper-slide v-for="(item, index) of imgs" :key="index">
          <img class="gallary-img" :src="item" />
        </swiper-slide>
        <div class="swiper-pagination" slot="pagination"></div>
      </swiper>
    </div>
  </div>
</template>

<script>
export default {
  name: "CommonGallary",
  props: {
    imgs: {
      type: Array,
      default() {
        return [];
      },
    },
  },
  data() {
    return {
      swiperOption: {
        pagination: ".swiper-pagination",
        paginationType: "fraction",
        // observeParant: true, //当Swiper插件只要监听到 我这个元素或父级元素 发生了DOM 结构的变化的时候, 我会自动的自我刷新一次,通过这次自我刷新,就可以解决swiper宽度计算的问题
        // observer: true,
      },
    };
  },
  methods: {
    handleGallaryClick() {
      this.$emit("close");
    },
  },
};
</script>

<style lang="scss" scoped>
.container >>> .swiper-container {
  overflow: inherit;
}
.container {
  z-index: 99;
  position: fixed;
  display: flex;
  flex-direction: column;
  justify-content: center;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: #000;
  .wrapper {
    height: 0;
    width: 100%;
    padding-bottom: 100%;
    .gallary-img {
      width: 100%;
    }
    .swiper-pagination {
      color: #fff;
      bottom: -1rem;
    }
  }
}
</style>