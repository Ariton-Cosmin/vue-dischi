<template>
  <div class="col-sm-6 col-md-4 col-lg-2">
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
div {
  border: solid 8px rgb(30, 45, 59);
  background-color: rgb(46, 58, 70);

  img {
    width: 150px;
    height: 150px;
    padding: 5px;
  }

  h2 {
    font-size: 20px;
    padding-bottom: 5px;
    padding-top: 5px;
    color: white;
  }

  h4 {
    font-size: 15px;
    color: gray;
  }
}
</style>