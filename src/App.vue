<script>
import Block from "./components/Block.vue";
import Result from "./components/Result.vue";
export default {
  name: "App",
  components: { Block, Result },
  data() {
    return {
      isPlaying: false,
      delay: 0,
      score: null,
      showscore: false
    };
  },
  methods: {
    start() {
      this.delay = 2000 + Math.random() * 5000;
      this.isPlaying = true;
      this.showscore = false
    },
    endGame(reactionTime) {
      this.isPlaying = false;
      this.score = reactionTime;
      this.showscore = true;
      console.log(this.score);
    }
  }
};

</script>

<template>
  <div class="content">
    <h1>JackDev reaction Timer</h1>
    <button @click="start" :disabled="isPlaying">Play</button>
    <Block v-if="isPlaying" :delay="delay" @end="endGame" />
    <Result v-if="showscore" :score="score" />

  </div>
</template>

<style  scoped lang="scss">
.content {
  display: flex;
  flex-direction: column;

  h1 {
    text-align: center;
  }

  button {
    padding: 0 40px;
    height: 45px;
    margin: 0 auto;
    font-size: 1rem;
    border-radius: 10px;
    background-color: transparent;
    color: white;
    border: 2px solid#fff;
    outline: none;
    cursor: pointer;
  }

}
</style>
