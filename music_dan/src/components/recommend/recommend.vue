<template>
  <div>
    <slider :data="recommends"></slider>
  </div>
</template>

<script>
import { getRecommend } from '@/api/recommend'
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
  },
  methods: {
    _getRecommend () {
      getRecommend().then((res) => {
        console.log(res, 'res')
        if (res.code === ERR_OK) {
          this.recommends = res.data.slider
        }
      })
    }
  }
}
</script>

<style>
</style>
