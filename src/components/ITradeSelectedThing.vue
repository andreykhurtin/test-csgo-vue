<template>
  <div class="trade-selected-thing">
    <template v-if="data">
      {{ data.name }}
    </template>
  </div>
</template>

<script>
export default {
  name: "ITradeSelectedThing",
  props: ["data"],
};
</script>

<style lang="stylus" scoped>
.trade-selected-thing
  width 322px
  height 322px
  font-size 36px
  font-weight bold
  display flex
  justify-content center
  align-items center
  text-align center
</style>
