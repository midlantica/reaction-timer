<template>
  <div class="block" v-if="showBlock" @click="stopTimer">Click me!</div>
</template>

<script>
  export default {
    name: 'Block',
    props: ['delay'],
    data() {
      return {
        showBlock: false,
        timer: null,
        reactionTime: 0,
      }
    },
    mounted() {
      setTimeout(() => {
        this.showBlock = true
        this.startTimer()
      }, this.delay)
    },
    methods: {
      startTimer() {
        this.timer = setInterval(() => {
          this.reactionTime += 10
        }, 10)
      },
      stopTimer() {
        clearInterval(this.timer)
        console.log(this.reactionTime);
        this.$emit('end', this.reactionTime)
      }
    },
    computed() {
      reactionTime = reactionTime(Math.floor((ms/1000/60) << 0))
    }
  }
</script>

<style>
  .block {
    width: 25rem;
    border-radius: 1rem;
    background: #0faf87;
    color: white;
    text-align: center;
    padding: 7rem 0;
    margin: 4rem auto;
    cursor: pointer;
  }
</style>
