<template>
  <div class="App_tracker" @mousemove="bodyMove">
    <Tracker_Uni tracker='tracker' v-bind:style="{'left': x, 'top': y}" />
  </div>
</template>

<script>
import Tracker_Uni from './components/Tracker.vue'

export default {
  name: 'App',
  components: {
    Tracker_Uni,
  },
  data() {
    return {
      x: 50,
      y: 50
    }
  },
  methods: {
    bodyMove: function(e) {
      this.x = `${e.clientX}px`;
      this.y = `${e.clientY}px`;
    }
  }
}
</script>

<style lang="less">

  @import './styles/variables';

  .App {
    &_tracker {
      background-image: url(./assets/space_1.jpg);
      .bg_img();
      height: 100vh;
      overflow-x: hidden;
      .flex_cor();
      cursor:  url(./assets/spaceman.png) 2 2, pointer;

      @media (max-width: @mobil-landscape) and (orientation: landscape) {
        cursor: none;
      }

      @media (max-width: @tablet) {
        cursor: none;
      }

      @media (max-width: @mobil) {
        background-position: left;
        cursor: none;
      }
    }
  }
</style>
