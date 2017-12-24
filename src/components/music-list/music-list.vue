<template>
  <div class="music-list">
    <div class="back"></div>
    <h1 class="title"></h1>
    <div class="bg-image"></div>
    <div class="bg-layer"></div>
    <scroll class="list" ref="list"></scroll>
  </div>
</template>

<script type="text/ecmascript-6">
  export default {}
</script>

<style lang="stylus" rel="stylesheet/stylus">
  @import "~common/stylus/variable"
  @import "~common/stylus/mixin"

  .music-list
    position fixed
    z-index 100
    top 0
    left 0
    right 0
    bottom 0
    background $color-background
    .back
      position absolute
      top 0
      left 6px
      z-index 50
      .icon-back
        display block
        padding 10px
        font-size $font-size-large-x
        color $color-theme
    .title
      position absolute
      top 0
      left 10%
      z-index 40
      width 80%
      no-wrap()
      text-align center
      line-height 40px
      font-size $font-size-large
      color $color-text
    .bg-image
      position relative
      width 100%
      height 0
      padding-top 70%
      transform-origin top
      background-size cover
    .bg-layer
      position relative
      height 100%
      background $color-background
    .list
      position fixed
      top 0
      bottom 0
      width 100%
      background $color-background
</style>
