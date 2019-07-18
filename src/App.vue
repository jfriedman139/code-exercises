<template>
  <div id="app">
    <MapWidget/>
    <FoodWidget/>
  </div>
</template>

<script>
import '../public/reset.scss';
import MapWidget from './components/MapWidget.vue';
import FoodWidget from './components/FoodWidget.vue';

export default {
  name: 'app',
  components: {
    MapWidget,
    FoodWidget,
  },
};
</script>

<style lang="scss">
</style>
