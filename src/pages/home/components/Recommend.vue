<template>
  <div>
    <div class="title">熱銷推薦</div>
    <ul>
      <router-link
        tag="li"
        class="border-bottom item"
        v-for="item of list"
        :key="item.id"
        :to="`/detail/${item.id}`"
      >
        <img class="item-img" :src="item.imgUrl" />
        <div class="item-info">
          <p class="item-title">{{ item.title }}</p>
          <p class="item-desc">{{ item.desc }}</p>
          <button class="item-button">查看詳情</button>
        </div>
      </router-link>
    </ul>
  </div>
</template>

<script>
export default {
  name: "HomeRecommend",
  props: {
    list: Array,
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
  overflow: hidden;
  display: flex;
  height: 1.9rem;
  &-img {
    width: 1.7rem;
    height: 1.7rem;
    padding: 0.1rem;
  }
  &-info {
    overflow: hidden;
    flex: 1;
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
  &-button {
    line-height: 0.44rem;
    margin-top: 0.16rem;
    background: #ff9300;
    padding: 0 0.2rem;
    border-radius: 0.06rem;
    color: #fff;
  }
}
</style>