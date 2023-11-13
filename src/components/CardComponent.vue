<template>
  <div class="col-3">
    <div>
      <div><img :src="image" :alt="name" /></div>
      <div class="text-center py-2">
        <h4>{{ name }}</h4>
        <h5>{{ archetype }}</h5>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "CardComponent",
  props: {
    image: String,
    name: String,
    archetype: String
  },
};
</script>

<style lang="scss" scoped>
img {
  width: 100%;
}
</style>
