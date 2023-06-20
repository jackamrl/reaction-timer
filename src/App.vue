<script >
import Block from "./components/Block.vue";
export default {
  name: "App",
  components: { Block },
  data() {
    return {
      isPlaying: false,
      delay: 0,
    };
  },
  methods: {
    start() {
      this.delay = 2000 + Math.random() * 5000;
      this.isPlaying = true;
    }
  }
};

</script>

<template>
  <div class="content">
    <h1>JackDev reaction Timer</h1>
    <button @click="start" :disabled="isPlaying">Play</button>
    <Block v-if="isPlaying" :delay="delay" />
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
