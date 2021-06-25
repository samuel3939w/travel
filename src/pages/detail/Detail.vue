<template>
  <div>
    <detail-banner></detail-banner>
    <detail-header></detail-header>
    <div class="content">
      <detail-list :list="list"></detail-list>
    </div>
  </div>
</template>

<script>
import DetailBanner from "./components/Banner.vue";
import DetailHeader from "./components/Header.vue";
import DetailList from "./components/List.vue";

export default {
  name: "Detail",
  data() {
    return {
      list: [
        {
          title: "成人票",
          children: [
            {
              title: "成人三館聯票",
              children: [
                {
                  title: "成人三館聯票 - 某一連鎖店銷售",
                },
              ],
            },
            {
              title: "成人五館聯票",
            },
          ],
        },
        {
          title: "學生票",
        },
        {
          title: "兒童票",
        },
        {
          title: "特惠票",
        },
      ],
    };
  },
  components: {
    DetailBanner,
    DetailHeader,
    DetailList,
  },
};
</script>

<style lang="scss" scoped>
.content {
  height: 50rem;
}
</style>