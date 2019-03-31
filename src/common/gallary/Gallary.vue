<template>
    <div class="container" @click="handleGallaryClick">
        <div class="wrapper">
            <swiper :options="swiperOptions" v-for="(item, index) in imgs" :key="index">
                <swiper-slide>
                    <img class="gallary-img" :src="item">
                </swiper-slide>
                <div class="swiper-pagination"  slot="pagination"></div>
                <!-- <div class="swiper-button-prev" slot="button-prev"></div>
                <div class="swiper-button-next" slot="button-next"></div>
                <div class="swiper-scrollbar"   slot="scrollbar"></div> -->
            </swiper>
        </div>
    </div>
</template>

<script>
export default {
  name: 'CommonGallary',
  props: {
    imgs: {
      type: Array,
      default () {
        return []
      }
    }
  },
  data () {
    return {
      swiperOptions: {
        pagination: 'swiper-pagination',
        paginationType: 'fraction',
        observeParents: true,
        observer: true
      }
    }
  },
  methods: {
    handleGallaryClick () {
      this.$emit('close')
    }
  }
}
</script>

<style lang="stylus" scoped>
    .container >>> .swiper-pagination
      overflow: inherit
    .container
      z-index: 99
      display: flex
      flex-direction: column
      justify-content: center
      position: fixed
      left: 0
      right: 0
      top: 0
      bottom: 0
      background: #000
      .wrapper
        overflow: hidden
        height: 0
        width: 100%
        padding-bottom: 60%
        .gallary-img
          width: 100%
        .swiper-pagination
          color: #fff
          bottom: -1rem
</style>
