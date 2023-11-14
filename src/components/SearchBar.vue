<template>
  <div>
      <select name="searchbar" id="searchbar" v-model="textSearch" @change="passData">
        <option value="">All</option>
        <option value="Alien">Alien</option>
        <option value="Artifact">Artifact</option>
        <option value="Goblin">Goblin</option>
        <option value="Monarch">Monarch</option>
        <option value="Pendulum">Pendulum</option>
        <option value="Volcanic">Volcanic</option>        
      </select>
  </div>
</template>

<script>
export default {
  name: 'SearchBar',
  data() {
      return {
      textSearch: ''
    }
  },
  methods: {
    passData() {
      this.$emit('filterChange', this.textSearch);
    }
  }
}
</script>

<style lang="scss" scoped></style>