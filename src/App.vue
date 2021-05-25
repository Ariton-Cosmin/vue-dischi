<template>
  <div id="app">
    <div class="top mb-5">
      <img src="./assets/img/logo-small.svg" alt="" />
    </div>

    <div class="container text-center mt-3">
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
      .then((response) => {
        this.songs = response.data.response;
      })
      .catch((err) => {
        console.log(err);
      });
  },
};
</script>

<style lang="scss">
@import "@/assets/style/general.scss";

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  background-color: rgb(30, 45, 59);
}

.top {
  width: 100%;
  height: 50px;
  padding: 5px;
  background-color: rgb(46, 58, 70);

  img {
    width: 35px;
  }
}
</style>
