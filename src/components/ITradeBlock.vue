<template>
  <div class="trade-block">
    <section class="trade-block__top section">
      <IUserSelectedThings
        :data="activeUserItems"
        :limit="userLimit"
        class="trade-block__user-select section"
      />
      <ITradeSelectedThing
        :data="activeTradeItem"
        class="trade-block__trade section"
      />
    </section>
    <div class="trade-block__main">
      <IThingsList
        class="trade-block__box section _left"
        :data="userItems"
        :choose-limit="userLimit"
        @change="changeUserList"
      />
      <IThingsList
        class="trade-block__box section _right"
        :data="tradeItems"
        :choose-limit="tradeLimit"
        @change="changeTradeItem"
      />
    </div>
  </div>
</template>

<script>
import IThingsList from "@/components/IThingsList";
import IUserSelectedThings from "@/components/IUserSelectedThings";
import ITradeSelectedThing from "@/components/ITradeSelectedThing";

import { ref, computed } from "vue";
import { useStore } from "vuex";
export default {
  name: "ITradeBlock",
  components: { IThingsList, IUserSelectedThings, ITradeSelectedThing },
  setup() {
    const store = useStore();

    const userLimit = 6;
    const tradeLimit = 1;
    const activeTradeItem = ref(null);
    const activeUserItems = ref([]);
    const userItems = computed(() => store.state.userItems);
    const tradeItems = computed(() => store.state.tradeItems);

    const changeUserList = (list) => (activeUserItems.value = list);

    const changeTradeItem = (item) => {
      activeTradeItem.value = item;
    };

    //activeTradeItem, activeUserItems - что-то делаем с этим в дальшнейшем

    return {
      userItems,
      tradeItems,
      activeUserItems,
      activeTradeItem,
      userLimit,
      tradeLimit,
      changeUserList,
      changeTradeItem,
    };
  },
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
