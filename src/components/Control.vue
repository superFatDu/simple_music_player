<template>
  <div class="control" :class="{ control_playing: isPlaying }">
    <div class="control_btn control_btn_side" @click="handlePrev">
      <i class="icon">&#xe61d;</i>
    </div>
    <div class="control_btn control_btn_side" @click="handlePlay">
      <!-- <span class="icon" :class="{ 'iconziyuanldpi3': isPlaying === true, 'iconziyuanldpi': isPlaying === false }" />> -->
      <i class="icon" v-show="isPlaying">&#xe61c;</i>
      <i class="icon" v-show="!isPlaying">&#xe61f;</i>
    </div>
    <div class="control_btn control_btn_side" @click="handleNext">
      <i class="icon">&#xe61e;</i>
    </div>
  </div>
</template>

<script>
import { mapState } from 'vuex'
import { player } from '../player'
export default {
  name: 'control',
  computed: {
    ...mapState(['isPlaying'])
  },
  methods: {
    handlePrev () {
      if (this.isPlaying) {
        player.prev()
      }
    },
    handlePlay () {
      if (!player.isEmpty) {
        if (!this.isPlaying) {
          player.play()
        } else {
          player.pause()
        }
      }
    },
    handleNext () {
      if (this.isPlaying) {
        player.next()
      }
    }
  }
}
</script>

<style lang="scss" scoped>
.control {
  display: flex;
  width: 100%;
  .control_btn {
    display: flex;
    margin:2px;
    align-items: center;
    justify-content: center;
    flex: 1;
    border-radius: 4px;
    color: #cccccc;
    font-size: 16px;
    transition: background-color .6s ease;
    &:hover {
      background-color: #dddddd;
      color: #ffffff;
    }
  }
  .control_btn_side {
    font-size: 14px;
  }
}
</style>
