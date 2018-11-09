<template>
  <div class="tab">
   <router-link  class="tab__link" tag="div" to="/recommend">
     <span class="link__name">推荐</span>
   </router-link>
   <router-link tag="div" class="tab__link" to="/singer">
     <span class="link__name">歌手</span>
   </router-link>
   <router-link tag="div" class="tab__link" to="/rank">
     <span class="link__name">排行</span>
   </router-link>
   <router-link tag="div" class="tab__link" to="/search">
     <span class="link__name">搜索</span>
   </router-link>
  </div>
</template>

<script>
export default {

}
</script>

<style scoped lang="stylus" rel="stylesheet/stylus">
@import "~common/stylus/variable"
.tab
  display flex
  height 44px
  line-height 44px
  color $color-text
  font-size $font-size-medium
  .tab__link
    display inline-block
    text-align center
    flex 1
    .link__name
      padding-bottom 5px
    &.router-link-active
      .link__name
        color $color-theme
        border-bottom $color-theme 1px solid

</style>
