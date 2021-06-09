<template>
  <div id="app">
    <!-- HEADER -->
    <Header />
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
  }
}
</script>

<style lang="scss">
  @import '~bootstrap/scss/bootstrap.scss';
  @import '~@fortawesome/fontawesome-free/scss/fontawesome.scss';
  @import './style/general.scss';
  @import './style/variables.scss';
  @import './style/mixins.scss';

  
</style>
