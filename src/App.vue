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
      this.showscore = false;
    },

    endGame(reactionTime) {
      this.isPlaying = false;
      this.score = reactionTime;
      this.showscore = true;
    }
  }
};

</script>

<template>
  <div class="content">
    <h1>⏰</h1>
    <h1>Welcome to Reaction Timer Game </h1>
    <p v-if="!isPlaying">Once the game has started, click on the box below. 👇</p>
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
    font-size: 2.5rem;
    font-weight: 700;
  }

  p {
    text-align: center;
  }

  button {
    padding: 0 70px;
    height: 50px;
    margin: 30px auto;
    font-size: 1.2rem;
    border-radius: 10px;
    background-color: transparent;
    color: white;
    border: 2px solid#fff;
    outline: none;
    cursor: pointer;

    &:hover {
      background-color: rgb(39, 49, 46);
    }

    &:disabled {
      opacity: 0.5;
      cursor: not-allowed;

      &:hover {
        background-color: transparent;
      }
    }

  }

}
</style>
