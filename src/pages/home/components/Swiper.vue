<template>
 <div class="wrapper">
  <swiper :options="swiperOption">
    <swiper-slide v-for="item of swiperList" :key="item.id">
        <img class="swiper-img" :src="item.imgUrl">
    </swiper-slide>
    <div class="swiper-pagination" slot="pagination"></div>
  </swiper>
 </div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true
      },
      swiperList: [{
        id: '0001',
        imgUrl: 'https://www.travel.taipei/image/216049/compressed'
      }, {
        id: '0002',
        imgUrl: 'https://www.travel.taipei/image/215296/compressed'
      }]
    }
  }
}
</script>

<style lang="scss" scoped>

.wrapper >>> .swiper-pagination-bullet-active{
      background-color: #fff;
    }
.wrapper{
    overflow: hidden;
    width: 100%;
    height: 0;
    padding-bottom: 41.3%;
    background: #eee;
}
  .swiper-img{
      width: 100%;
  }
</style>
