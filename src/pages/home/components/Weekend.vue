<template>
  <div>
    <div class="title">熱銷推薦</div>
    <ul>
      <li
        class="border-bottom item"
        v-for="item of recommendList"
        :key="item.id"
      >
        <div class="item-img-wrapper">
          <img class="item-img" :src="item.imgUrl" />
        </div>

        <div class="item-info">
          <p class="item-title">{{ item.title }}</p>
          <p class="item-desc">{{ item.desc }}</p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "HomeRecommend",
  data() {
    return {
      recommendList: [
        {
          id: "0001",
          imgUrl:
            "http://img1.qunarzz.com/sight/source/1505/9f/f585152825459.jpg_r_640x214_5d46e4cc.jpg",
          title: "大連勝雅海洋世界",
          desc: "浪漫大連首站, 浪漫的海洋主題樂園",
        },
        {
          id: "0002",
          imgUrl:
            "http://img1.qunarzz.com/sight/source/1505/9f/f585152825459.jpg_r_640x214_5d46e4cc.jpg",
          title: "大連勝雅海洋世界",
          desc: "浪漫大連首站, 浪漫的海洋主題樂園",
        },
        {
          id: "0003",
          imgUrl:
            "http://img1.qunarzz.com/sight/source/1505/9f/f585152825459.jpg_r_640x214_5d46e4cc.jpg",
          title: "大連勝雅海洋世界",
          desc: "浪漫大連首站, 浪漫的海洋主題樂園",
        },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
@import "~styles/mixins.scss";

.title {
  margin-top: 0.2rem;
  line-height: 0.8rem;
  background: #eee;
  text-indent: 0.2rem;
}
.item {
  &-img-wrapper{
      overflow: hidden;
      height: 0;
      padding-bottom: 33.9%;
  }
  &-img {
    width: 100%;
  }
  &-info {
    overflow: hidden;
    padding: 0.1rem;
    font-family: "微軟正黑體";
  }
  &-title {
    line-height: 0.54rem;
    font-size: 0.32rem;
    @include ellipsis;
  }
  &-desc {
    line-height: 0.4rem;
    color: #ccc;
    @include ellipsis;
  }
}
</style>