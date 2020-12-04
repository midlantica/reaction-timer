<template>
  <div class="block" v-if="showBlock">
    Click me!
  </div>
</template>

<script>
export default {
  name: 'Block',
  props: ['delay'],
  data() {
    return {
      showBlock: false
    }
  },
  mounted() {
    console.log("component mounted")
    setTimeout(() => {
      this.showBlock = true
      console.log(this.delay)
    }, this.delay);
  },
  updated() {
    console.log('component updated')
  },
  unmounted(){
    console.log('component unmounted');
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
