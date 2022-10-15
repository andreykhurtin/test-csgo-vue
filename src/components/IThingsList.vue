<template>
  <section class="things-list">
    <IThingItem
      v-for="item in data"
      :key="item.id"
      :data="item"
      :active="isMultiple ? list.has(item) : activeSingleItem?.id === item.id"
      @click="isMultiple ? toggleMultipleItems(item) : toggleSingleItem(item)"
    />
  </section>
</template>

<script>
import IThingItem from "@/components/IThingItem";

import { ref, toRef } from "vue";
export default {
  name: "IThingsList",
  props: ["data", "chooseLimit"],
  components: { IThingItem },
  setup(props, { emit }) {
    const limit = toRef(props, "chooseLimit");
    const list = ref(new Set());
    let activeSingleItem = ref(null);
    const isMultiple = limit.value > 1;

    const toggleMultipleItems = (item) => {
      const outOfRange =
        !list.value.has(item) && list.value.size === limit.value;

      if (!outOfRange) {
        list.value.has(item) ? list.value.delete(item) : list.value.add(item);
        emit("change", Array.from(list.value.values()));
      }
    };

    const toggleSingleItem = (item) => {
      if (activeSingleItem.value?.id === item.id) {
        activeSingleItem.value = null;
      } else {
        activeSingleItem.value = item;
      }

      emit("change", activeSingleItem.value);
    };

    return {
      toggleMultipleItems,
      toggleSingleItem,
      list,
      activeSingleItem,
      isMultiple,
    };
  },
};
</script>

<style lang="stylus" scoped>
.things-list
  width 100%
  display grid
  grid-template-columns repeat(auto-fit, 112px)
  gap 10px
</style>
