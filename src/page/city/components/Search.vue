<template>
    <div class="search">
      <input type="text" placeholder="输入城市名/拼音" class="search-input">
    </div>
</template>

<script>
    export default {
        name: "CitySearch"
    }
</script>

<style scoped lang="stylus">
  @import "~styles/variables.styl"
  .search
    height: .72rem
    padding: .1rem
    background-color: $bgColor
    .search-input
      box-sizing : border-box
      width: 100%
      height: .62rem
      line-height: .62rem
      text-align : center
      padding: 0 .1rem
      color: #666
      border-radius : .06rem
</style>
