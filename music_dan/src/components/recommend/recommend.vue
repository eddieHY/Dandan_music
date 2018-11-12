<template>
  <div class="recommend">
    <div class="recommend-content">
      <slider v-if="recommends.length">
        <div v-for="(item, index) in recommends" :key="index">
          <a :href="item.linkUrl">
            <img class="needsclick" :src="item.picUrl">
          </a>
        </div>
      </slider>
      <div class="recommend-list">
        <h1 class="list-title">
        热门歌单推荐
        </h1>
        <ul></ul>
      </div>
    </div>
  </div>
</template>

<script>
import { getRecommend, getDiscoList } from '@/api/recommend'
import { ERR_OK } from '@/api/config'
import slider from '@/base/slider/slider'

export default {
  data () {
    return {
      recommends: []
    }
  },
  components: { slider },
  created () {
    this._getRecommend()
    this._getDiscList()
  },
  methods: {
    _getRecommend () {
      getRecommend().then((res) => {
        console.log(res, 'res')
        if (res.code === ERR_OK) {
          this.recommends = res.data.slider
        }
      })
    },
    _getDiscList () {
      getDiscoList().then((res) => {
        console.log(res, 'res')
      })
    },
    load () {

    }
  }
}
</script>

<style lang="stylus" scoped>
@import "~common/stylus/variable"
.recommend
  position fixed
  width 100%
  top 88px
  bottom 0
  .recommend-content
    height 100%
    overflow hidden
</style>
