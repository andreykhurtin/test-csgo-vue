<template>
  <ITradeBlock />
</template>

<script>
import ITradeBlock from "@/components/ITradeBlock";

export default {
  name: "App",
  components: { ITradeBlock },
};
</script>

<style lang="stylus">
#app
  font-family Avenir, Helvetica, Arial, sans-serif
  -webkit-font-smoothing antialiased
  -moz-osx-font-smoothing grayscale
  text-align center
  color #2c3e50
  margin-top 60px
*
  box-sizing border-box
.section
  width 100%
  padding 24px
  border 4px solid black
</style>
