<template>
    <div class="header">
      <div class="header-left">
        <div class="iconfont back-icon">&#xe675;</div>
      </div>
      <div class="header-input">
        <span class="iconfont">&#xe624;</span>
        输入城市/景点/游玩主题</div>
      <div class="header-right">
        城市
        <span class="iconfont arrow-icon">&#xe622;</span>
      </div>
    </div>
</template>

<script>
    export default {
        name: "HomeHeader"
    }
</script>

<style lang="stylus" scoped>
  @import "~styles/variables.styl"
 .header
   line-height: .86rem
   display: flex
   background-color: $bgColor
   color: #fff
   .header-left
     width: .64rem
     float: left
     .back-icon
       text-align: center
       font-size: .4rem
   .header-input
     flex:1
     height: .64rem
     margin-left: .2rem
     margin-top: .12rem
     padding-left: .2rem
     line-height: .64rem
     border-radius: .1rem
     background: #fff;
     color: #ccc
   .header-right
     width: 1.24rem
     text-align: center
     float: right
     .arrow-icon
       font-size : .1rem
       margin-left : -.04rem

</style>
