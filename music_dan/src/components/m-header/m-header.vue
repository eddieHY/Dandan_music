<template>
  <div class="m-header">
    <div class="m-header__logo"></div>
    <div class="m-header__title">Dandan Music</div>
    <div class="mine">
      <i class="icon-mine"></i>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
    }
  }
}
</script>

<style lang="stylus" scoped rel="stylesheet/stylus">
@import "~common/stylus/variable"
@import "~common/stylus/mixin"

.m-header
  position relative
  height 44px
  margin 0
  text-align center
  color $color-theme
  font-size 0
  .m-header__logo
    display inline-block
    width 30px
    height 32px
    bg-image('logo')
    background-size 30px 32px
    vertical-align top
    margin-top: 6px
    margin-right 6px
  .m-header__title
    display inline-block
    line-height 44px
    font-size: $font-size-large
  .mine
      position: absolute
      top: 0
      right: 0
      .icon-mine
        display: block
        padding: 12px
        font-size: 20px
        color: $color-theme
</style>
