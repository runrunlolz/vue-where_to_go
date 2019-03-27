<template>
    <div class="wrapper">
        <swiper :options="swiperOption">
            <swiper-slide v-for="item of swiperList" :key="item.id">
                <img class="swiper-img" :src="item.imgUrl">
            </swiper-slide>
            <div class="swiper-pagination"  slot="pagination"></div>
            <!-- <div class="swiper-button-prev" slot="button-prev"></div>
            <div class="swiper-button-next" slot="button-next"></div>
            <div class="swiper-scrollbar"   slot="scrollbar"></div> -->
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
        // autoplay: {
        //   delay: 5000,
        //   stopOnLastSlide: false,
        //   disableOnInteraction: true
        // }
      },
      swiperList: [{
        id: '0001',
        imgUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20193/ed5f4115226306e48e6fad106a038afe.jpg_750x200_64df48d6.jpg'
      }, {
        id: '0002',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1609/47/0cfdc871ac183702.jpg_750x200_f6896acd.jpg'
      }, {
        id: '0003',
        imgUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20193/c807f8e462d269397489ef90b16f61b7.jpg_750x200_aaf543ba.jpg'
      }, {
        id: '0004',
        imgUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20193/81743f7e8589990dd413cccadf315f8b.jpg_750x200_6f3f5164.jpg'
      }]
    }
  }
}
</script>

<style lang="stylus" scoped>
    .wrapper >>> .swiper-pagination-bullet-active
      background-color: #fff
    .wrapper
      width: 100%
      height: 0
      overflow: hidden
      padding-bottom: 27%
      background-color: #eee
      .swiper-img
        width: 100%
</style>
