<template>
  <div class="player">
    <div class="player_disk">
      <disk />
    </div>
    <div class="player_control">
      <control />
    </div>
    <div class="player_progress">
      <progress-bar />
    </div>
  </div>
</template>

<script>
import Disk from '../components/Disk.vue'
import Control from '../components/Control.vue'
import ProgressBar from '../components/ProgressBar.vue'

export default {
  name: 'player',
  components: {
    Disk,
    Control,
    ProgressBar
  }
}
</script>

<style lang="scss" scoped>
.player {
  position: relative;
  display: flex;
  max-width: 300px;
  max-height: 75px;
  width: 60vw;
  height: 15vw;
  border-radius: 8px;
  background-color: #ffffff;
  box-shadow: 0 30px 60px rgba(0, 0, 0, .12),
    0 20px 20px rgba(95, 23, 101, .2);
  .player_disk {
    flex: 1.2;
    padding: 2.4vw;
  }
  .player_control {
    flex: 2;
    padding: 2.4vw 0;
    padding-right: 2.4vw;
  }
  .player_progress {
    position: absolute;
    left: 1.8vw;
    right: 1.8vw;
    top: 0;
    bottom: 5vw;
    z-index: -1;
  }
}
</style>
