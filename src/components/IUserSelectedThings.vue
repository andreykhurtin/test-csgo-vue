<template>
  <section class="user-selected-things">
    <IThingItem
      v-for="item in 0"
      :key="item"
      :data="{ id: 1, name: `Shoes ${item}` }"
    />
  </section>
</template>

<script>
import IThingItem from "@/components/IThingItem";
export default {
  name: "IUserSelectedThings",
  components: { IThingItem },
};
</script>

<style lang="stylus" scoped>
.user-selected-things
    width 100%
    display grid
    grid-template-columns repeat(3, 1fr)
    gap 10px
</style>
