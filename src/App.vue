<template>
  <div id="app">
    <!-- HEADER -->
    <Header :image="logo" @changeGenre="changeType" />
    <!-- /HEADER -->

    <!-- MAIN -->
    <main>
      <DiscsList :discsGenre="musicGenre" :newArray="funzione" />
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
      musicGenre: ''
    }
  },
  methods: {
    changeType: function(genre) {
      this.musicGenre = genre;
    },
    funzione: function(array) {
      console.log(array);
    }
  },
}
</script>

<style lang="scss">
  @import './style/general.scss';

</style>
