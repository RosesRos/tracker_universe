<template>
  <div class="App_tracker" @mousemove="bodyMove">
    <Tracker_Uni tracker='tracker'/>
  </div>
</template>

<script>
import Tracker_Uni from './components/Tracker.vue'

export default {
  name: 'App',
  components: {
    Tracker_Uni
  },
  methods: {
    bodyMove: function(e) {
      var tracker = document.querySelector(".tracker");

      tracker.style.left = `${e.clientX}px`;
      tracker.style.top = `${e.clientY}px`;
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
