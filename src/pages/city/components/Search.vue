<template>
  <div class="search">
    <input type="text" class="search-input" placeholder="輸入城市名稱或拼音" />
  </div>
</template>

<script>
export default {
  name: "CitySearch",
};
</script>

<style lang="scss" scoped>
@import "~styles/varibles.scss";

.search {
  height: 0.72rem;
  padding: 0 0.1rem;
  background: $bgColor;
  &-input {
      box-sizing: border-box;
    height: 0.62rem;
    padding: 0 .1rem;
    line-height: 0.62rem;
    width: 100%;
    border-radius: 0.06rem;
    text-align: center;
    color: #666;
  }
}
</style>