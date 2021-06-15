<template>
    <div id="app">
      <Header 
      :genres="genres" 
      @changeGenre="passGenre"/>
      <Main @ready="genresOption" />
    </div>
</template>

<script>
import Header from "./components/Header"
import Main from "./components/Main"

export default {
    name: "App",
    data: function() {
      return {
        genres: []
      }
      
    },
    methods: {
      genresOption: function(array) {
        this.genres = array;
      },
      passGenre: function(genrePass) {
        console.log("genrePass: " + genrePass);
      }
    },
    components: {
      Header,
      Main
    }
      

}
</script>

<style lang="scss">
@import "./style/General";
    #app {
      color: white;
    }
    Header {
      height: $height-header;
      background-color: $bg-header;
    }
    Main {
      min-height: $height-main;
      background-color: $bg-main;
    }
</style>