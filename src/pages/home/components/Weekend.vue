<template>
  <div>
    <div class="title">熱銷推薦</div>
    <ul>
      <li
        class="border-bottom item"
        v-for="item of list"
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
  name: "HomeWeekend",
  props:{
    list:Array
  }
};
</script>

<style lang="scss" scoped>
@import "~styles/mixins.scss";

.title {
  line-height: 0.8rem;
  background: #eee;
  text-indent: 0.2rem;
}
.item {
  &-img-wrapper{
      overflow: hidden;
      height: 0;
      padding-bottom: 37.9%;
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