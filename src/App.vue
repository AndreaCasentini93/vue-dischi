<template>
  <div id="app">
    <!-- HEADER -->
    <Header :image="logo" />
    <!-- /HEADER -->

    <!-- MAIN -->
    <main>
      <DiscsList />
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
      logo: require('./assets/img/spotify.png')
    }
  }
}
</script>

<style lang="scss">
  @import './style/general.scss';

</style>
