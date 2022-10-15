<template>
  <section class="user-selected-things">
    <IThingItem v-for="item in data" :key="item.id" :data="item" />
    <span class="user-selected-things__info">
      Выбрано {{ data.length }} из {{ limit }}</span
    >
  </section>
</template>

<script>
import IThingItem from "@/components/IThingItem";
export default {
  name: "IUserSelectedThings",
  props: ["data", "limit"],
  components: { IThingItem },
};
</script>

<style lang="stylus" scoped>
.user-selected-things
  width 100%
  position relative
  display grid
  grid-template-columns repeat(auto-fit, 112px)
  gap 10px
  padding-bottom 40px
  &__info
    width 100%
    position absolute
    left 0
    right 0
    bottom 5px
    display block
    text-align center
    font-size 24px
    font-weight 600
</style>
