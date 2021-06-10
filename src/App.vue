<template>
  <div id="app">
    <!-- HEADER -->
    <Header :image="logo" :genresArray="genresArrayImport" :authorsArray="authorsArrayImport" @discsGenre="discsGenre" @discsAuthor="discsAuthor"/>
    <!-- /HEADER -->

    <!-- MAIN -->
    <main>
      <DiscsList @genresArray="genresArray" @authorsArray="authorsArray" :discsGenreImport="discsGenreImport" :discsAuthorImport="discsAuthorImport"/>
    </main>
    <!-- /MAIN -->
  </div>
</template>

<script>
import Header from './components/Header.vue';
import DiscsList from './components/DiscsList.vue';

export default {
  name: 'App',
  components: {
    Header,
    DiscsList
  },
  data: function() {
    return {
      logo: require('./assets/img/spotify.png'),
      musicGenre: '',
      genresArrayImport: [],
      authorsArrayImport: [],
      discsGenreImport: '',
      discsAuthorImport: ''
    }
  },
  methods: {
    genresArray: function(array) {
      this.genresArrayImport = array;
    },
    authorsArray: function(array) {
      this.authorsArrayImport = array;
    },
    discsGenre: function(string) {
      this.discsGenreImport = string;
    },
    discsAuthor: function(string) {
      this.discsAuthorImport = string;
    }
  }
}
</script>

<style lang="scss">
  @import './style/general.scss';

</style>
