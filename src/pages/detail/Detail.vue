<template>
    <div>
        <detail-banner :sightName="sightName" :bannerImg="bannerImg" :bannerImgs="gallaryImg"></detail-banner>
        <detail-header></detail-header>
        <div class="content">
            <detail-list :list="list"></detail-list>
        </div>
    </div>
</template>

<script>
import DetailBanner from './components/banner'
import DetailHeader from './components/header'
import DetailList from './components/list'
import axios from 'axios'
export default {
  name: 'Detail',
  components: {
    DetailBanner,
    DetailHeader,
    DetailList
  },
  data () {
    return {
      sightName: '',
      bannerImg: '',
      gallaryImg: [],
      list: []
    }
  },
  methods: {
    getDerailInfo () {
      axios.get('/api/detail.json?id', {
        params: {
          id: this.$route.params.id
        }
      }).then(this.handleGetDataSuccess)
    },
    handleGetDataSuccess (res) {
      res = res.data
      if (res.ret && res.data) {
        const data = res.data
        this.sightName = data.sightName
        this.bannerImg = data.bannerImg
        this.gallaryImg = data.gallaryImgs
        this.list = data.categoryList
      }
    }
  },
  mounted () {
    this.getDerailInfo()
  }
}
</script>

<style lang="stylus" scoped>
    .content
      height: 50rem
</style>
