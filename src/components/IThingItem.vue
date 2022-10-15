<template>
  <div class="thing-item">
    {{ data.name }}
  </div>
</template>

<script>
export default {
  name: "IThingItem",
  props: ["data"],
};
</script>

<style lang="stylus" scoped>
.thing-item
    width 112px
    height 112px
    border 4px solid black
    font-size 24px
    font-weight bold
    cursor pointer
    display flex
    justify-content center
    align-items center
    text-align center
</style>
