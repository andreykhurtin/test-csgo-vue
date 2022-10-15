<template>
  <div class="thing-item" :class="{ _active: active }">
    {{ data.name }}
  </div>
</template>

<script>
export default {
  name: "IThingItem",
  props: ["data", "active"],
};
</script>

<style lang="stylus" scoped>
.thing-item
  width 112px
  height 112px
  border 4px solid black
  font-size 18px
  font-weight bold
  cursor pointer
  display flex
  justify-content center
  align-items center
  text-align center
  &._active
    border-color blue
</style>
