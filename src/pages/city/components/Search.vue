<template>
  <div>
    <div class="search">
      <input
        v-model="keyword"
        type="text"
        class="search-input"
        placeholder="輸入城市名稱或拼音"
      />
    </div>
    <div class="search-content" ref="search" v-show="keyword">
      <ul>
        <li
          class="search-content-item border-bottom"
          v-for="item of list"
          :key="item.id"
          @click="handleCityClick(item.name)"
        >
          {{ item.name }}
        </li>
        <li class="search-content-item border-bottom" v-show="hasNoData">
          沒有找到匹配數據
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import Bscroll from "better-scroll";
import { mapMutations } from "vuex";

export default {
  name: "CitySearch",
  props: {
    cities: Object,
  },
  data() {
    return {
      keyword: "",
      list: [],
      timer: null,
    };
  },
  computed: {
    hasNoData() {
      return !this.list.length;
    },
  },
  methods: {
    handleCityClick(city) {
      this.changeCity(city);
      this.$router.push("/");
    },
    ...mapMutations(["changeCity"]),
  },
  mounted() {
    this.scroll = new Bscroll(this.$refs.search, { click: true });
  },
  updated() {
    if (this.scroll) {
      this.scroll.refresh();
    }
  },
  watch: {
    keyword() {
      if (this.timer) {
        clearTimeout(this.timer);
      }
      if (!this.keyword) {
        this.list = [];
        return;
      }
      this.timer = setTimeout(() => {
        const result = [];
        for (let i in this.cities) {
          this.cities[i].forEach((value) => {
            if (
              value.spell.indexOf(this.keyword) > -1 ||
              value.name.indexOf(this.keyword) > -1
            ) {
              result.push(value);
            }
          });
        }
        this.list = result;
      }, 100);
    },
  },
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
    padding: 0 0.1rem;
    line-height: 0.62rem;
    width: 100%;
    border-radius: 0.06rem;
    text-align: center;
    color: #666;
  }
}
.search-content {
  overflow: hidden;
  z-index: 1;
  position: absolute;
  top: 1.58rem;
  bottom: 0;
  right: 0;
  left: 0;
  background: #eee;
  &-item {
    line-height: 0.62rem;
    padding-left: 0.2rem;
    color: #666;
    background: #fff;
  }
}
</style>