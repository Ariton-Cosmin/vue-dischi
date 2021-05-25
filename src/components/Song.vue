<template>
  <div class="col-sm-6 col-md-4 col-lg-3">
    <img :src="song.poster" alt="" />
    <h2>{{ song.title }}</h2>
    <h4>{{ song.author }}</h4>
  </div>
</template>

<script>
export default {
  name: "Song",
  props: {
    song: Object,
  },
};
</script>

<style lang="scss" scoped>
img {
  width: 150px;
  height: 150px;
}
</style>