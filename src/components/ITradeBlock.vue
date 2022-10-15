<template>
  <div class="trade-block">
    <section class="trade-block__top section">
      <IUserSelectedThings class="trade-block__user-select section" />
      <ITradeSelectedThing
        :data="{ id: 1, name: 'Shoes 2' }"
        class="trade-block__trade section"
      />
    </section>
    <div class="trade-block__main">
      <IThingsList class="trade-block__box section _left" />
      <IThingsList class="trade-block__box section _right" />
    </div>
  </div>
</template>

<script>
import IThingsList from "@/components/IThingsList";
import IUserSelectedThings from "@/components/IUserSelectedThings";
import ITradeSelectedThing from "@/components/ITradeSelectedThing";
export default {
  name: "ITradeBlock",
  components: { IThingsList, IUserSelectedThings, ITradeSelectedThing },
};
</script>

<style lang="stylus" scoped>
.trade-block
  width 100%
  &__top
    width 100%
    margin-bottom 56px
    min-height 256px
    display flex
    justify-content space-between
  &__user-select
    width 424px
  &__main
    display flex
    justify-content space-between
  &__box
    width calc(50% - 12px)
    min-height 346px
    &:first-child
      margin-right 24px
</style>
