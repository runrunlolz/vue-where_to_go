<template>
    <div>
        <div class="banner" @click="handleBannerClick">
            <img class="banner-img" src="//img1.qunarzz.com/sight/p0/1801/4e/4ee5653be58dcb1a3.water.jpg_600x330_f82a1d80.jpg">
            <div class="banner-info">
                <div class="banner-title">大连</div>
                <div class="banner-number">
                    <span class="iconfont banner-icon">&#xe663;</span>
                    39
                </div>
            </div>
        </div>
        <common-gallary :imgs="imgs" v-show="showGallary" @close="handleGallaryClose"></common-gallary>
    </div>
</template>

<script>
import CommonGallary from 'common/gallary/Gallary'
export default {
  name: 'DetailBanner',
  components: {
    CommonGallary
  },
  data () {
    return {
      showGallary: false,
      imgs: []
    }
  },
  methods: {
    handleBannerClick () {
      this.showGallary = true
    },
    handleGallaryClose () {
      this.showGallary = false
    }
  }
}
</script>

<style lang="stylus" scoped>
    .banner
      overflow: hidden
      position: relative
      height: 0
      padding-bottom: 55%
      .banner-img
        width: 100%
      .banner-info
        display: flex
        position: absolute
        left: 0
        right: 0
        bottom: 0
        line-height: .6rem
        color: #fff
        background-image: linear-gradient(top, rgba(0,0,0,0), rgba(0,0,0,0.8))
        .banner-title
          flex: 1
          font-size: .32rem
          padding: 0 .2rem
        .banner-number
          margin-top: .14rem
          padding: 0 .4rem
          height: .32rem
          line-height: .32rem
          border-radius: .2rem
          background: rgba(0,0,0,.8)
          font-size: .24rem
          .banner-icon
            font-size: .24rem
</style>
