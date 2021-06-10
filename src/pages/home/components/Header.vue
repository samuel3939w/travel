<template>
  <div class="header">
    <div class="header-left">
      <div class="iconfont back-icon">&#xe624;</div>
    </div>
    <div class="header-input">
      <span class="iconfont">&#xe632;</span>
      輸入城市/景點/遊玩主題
    </div>
    <div class="header-right">
      城市
      <span class="iconfont arrow-icon">&#xe64a;</span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HomeHeader'
}
</script>

<style lang="scss" scoped>
@import '~styles/varibles.scss';

.header {
  display: flex;
  line-height: 0.86rem;
  background: $bgColor;
  color: #fff;
  &-left {
    width: 0.64rem;
    float: left;
    .back-icon{
      text-align: center;
      font-size: .4rem;
    }
  }
  &-input {
    flex: 1;
    height: 0.64rem;
    line-height: 0.64rem;
    margin-top: .12rem;
    margin-left: 0.2rem;
    padding-left: 0.2rem;
    background: #fff;
    border-radius: .1rem;
    color: #ccc;
  }
  &-right {
    width: 1.24rem;
    float: right;
    text-align: center;
    .arrow-icon{
      margin-left: -0.04rem;
      font-size: .24rem;
    }
  }
}
</style>
