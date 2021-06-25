<template>
  <div>
    <div class="banner" @click="handleBannerClick">
      <img
        class="banner-img"
        src="http://img1.qunarzz.com/sight/p0/201404/23/04b92c99462687fa1ba45c1b5ba4ad77.jpg_600x330_bf9c4904.jpg"
      />
      <div class="banner-info">
        <div class="banner-info-title">大連聖亞海洋世界(AAAA景區)</div>
        <div class="banner-info-number">
          <span class="iconfont banner-info-icon">&#xe692;</span> 39
        </div>
      </div>
    </div>
    <common-gallary
      :imgs="imgs"
      v-if="showGallary"
      @close="handleGallaryClose"
    ></common-gallary>
  </div>
</template>

<script>
import CommonGallary from "common/gallary/Gallary.vue";

export default {
  name: "DetailBanner",
  data() {
    return {
      showGallary: false,
      imgs: [
        "http://img1.qunarzz.com/sight/p0/201404/23/04b92c99462687fa1ba45c1b5ba4ad77.jpg_800x800_70debc93.jpg",
        "http://img1.qunarzz.com/sight/p0/1709/76/7691528bc7d7ad3ca3.img.png_800x800_9ef05ee7.png",
      ],
    };
  },
  components: {
    CommonGallary,
  },
  methods: {
    handleBannerClick() {
      this.showGallary = true;
    },
    handleGallaryClose() {
      this.showGallary = false;
    },
  },
};
</script>

<style lang="scss" scoped>
.banner {
  position: relative;
  overflow: hidden;
  height: 0;
  padding-bottom: 55%;
  &-img {
    width: 100%;
  }
  &-info {
    position: absolute;
    display: flex;
    left: 0;
    right: 0;
    bottom: 0;
    line-height: 0.6rem;
    color: #fff;
    background: linear-gradient(top, rgba(0, 0, 0, 0), rgba(0, 0, 0, 0.8));
    &-title {
      flex: 1;
      font-size: 0.32rem;
      padding: 0 0.2rem;
    }
    &-number {
      height: 0.32rem;
      line-height: 0.32rem;
      margin-top: 0.14rem;
      padding: 0 0.4rem;
      border-radius: 0.2rem;
      background: rgba(0, 0, 0, 0.8);
      font-size: 0.24rem;
    }
    &-icon {
      font-size: 0.24rem;
    }
  }
}
</style>