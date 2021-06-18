<template>
  <div class="header">
    城市選擇
    <router-link to="/">
      <div class="iconfont header-back">&#xe624;</div>
    </router-link>
  </div>
</template>

<script>
export default {
  name: "CityHeader",
};
</script>

<style lang="scss" scoped>
@import '~styles/varibles.scss';

.header {
  position: relative;
  overflow: hidden;
  height: $headerHeight;
  line-height: $headerHeight;
  text-align: center;
  color: #fff;
  background: $bgColor;
  &-back{
    position: absolute;
    top: 0;
    left: 0;
    width: 0.64rem;
    color: #fff;
    text-align: center;
    font-size: .32rem;
  }
}
</style>