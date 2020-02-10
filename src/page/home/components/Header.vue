<template>
    <div class="header">
      <div class="header-left">
        <div class="iconfont back-icon">&#xe675;</div>
      </div>
      <div class="header-input">
        <span class="iconfont">&#xe624;</span>
        输入城市/景点/游玩主题</div>
      <router-link to="/city">
        <div class="header-right">
          {{city}}
          <span class="iconfont arrow-icon">&#xe622;</span>
        </div>
      </router-link>
    </div>
</template>

<script>
    export default {
        name: "HomeHeader",
        props : {
          city : String
        }
    }
</script>

<style lang="stylus" scoped>
  @import "~styles/variables.styl"
 .header
   line-height: $headerHeight
   display: flex
   background-color: $bgColor
   color: $textDefaultColor
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
     background: $textDefaultColor
     color: #ccc
   .header-right
     width: 1.24rem
     text-align: center
     float: right
     color: $textDefaultColor
     .arrow-icon
       font-size : .1rem
       margin-left : -.04rem

</style>
