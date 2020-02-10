<template>
    <div class="header">
      城市选择
      <router-link to="/">
        <div class="iconfont city-back">&#xe675;</div>
      </router-link>
    </div>
</template>

<script>
    export default {
        name: "CityHeader"
    }
</script>

<style scoped lang="stylus">
  @import "~styles/variables.styl"
  .header
    position: relative
    overflow: hidden
    height: $headerHeight
    line-height: $headerHeight
    background-color: $bgColor;
    font-size: .32rem
    color: $textDefaultColor
    text-align: center
    .city-back
      position: absolute
      top: 0
      left: 0
      font-size: .4rem
      color: $textDefaultColor

</style>
