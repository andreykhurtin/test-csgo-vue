<template>
  <section class="things-list">
    <IThingItem
      v-for="item in 10"
      :key="item"
      :data="{ id: 1, name: `Shoes ${item}` }"
    />
  </section>
</template>

<script>
import IThingItem from "@/components/IThingItem";
export default {
  name: "IThingsList",
  components: { IThingItem },
};
</script>

<style lang="stylus" scoped>
.things-list
    width 100%
    display grid
    grid-template-columns repeat(8, 1fr)
    gap 10px
</style>
