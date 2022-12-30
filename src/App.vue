<template >
  <h1 class="text-3xl font-bold space-y-4 text-gray-700 mt-5 text-center ">How fast can u catch me ?</h1>
  <div class="text-center space-x-5">
    <button @click="start"
      class=" :disabled='isplaying' px-3 text-sm mt-4 py-[0.1rem] border font-bold hover:text-white border-blue-600 hover:bg-blue-500 rounded-sm duration-300 text-center ">play</button>
      <button @click="starttwo" v-if="playagain" class="px-3 text-sm mt-4 py-[0.1rem] border font-bold hover:text-white border-blue-600 hover:bg-blue-500 rounded-sm duration-300 text-center ">play again</button>
  </div>
  <div v-if="isplaying">
    <Block :dt="dt" @endgame="endgame" />
  </div>
  <div v-if="end">
    <Result :score="score" />
  </div>
</template>

<script>
import Block from './components/Block.vue'
import Result from './components/Result.vue'


export default {
  components: {
    Block,
    Result
  },
  data() {
    return {
      isplaying: false,
      dt: null,
      score: 0,
      end: false,
      playagain : false,
    }
  },
  methods: {
    start() {
      this.isplaying = true;
      this.dt = 1000 + Math.random() * 3000
    },
    starttwo(){
      this.isplaying = true;
      this.dt = 1000 + Math.reandom() * 3000
    },
    endgame(score) {
      this.score = score;
      this.isplaying = false;
      this.end = true,
      this.playagain = true
    }
  },


}
</script>

<style>

</style>