<template>
  <div id="app">
    <div class="container text-center mt-3">
      <h1>Vue Dischi</h1>

      <div class="row">
        <Song v-for="(song, index) in songs" :key="index" :song="song" />
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";
import Song from "./components/Song.vue";

export default {
  name: "App",
  components: {
    Song,
  },

  data() {
    return {
      axios,
      songs: [],
    };
  },

  created() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((res) => {
        this.songs = res.data;
      })
      .catch((err) => {
        console.log(err);
      });
  },
};
</script>

<style lang="scss">
@import "@/assets/style/general.scss";
</style>
