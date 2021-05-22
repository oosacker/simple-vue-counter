<template>
  <div class="counter">
    <h1 class="counter__heading">My Counter</h1>
    <h3 class="counter__count">{{ count }}</h3>
    <p>{{ startVal }}</p>
    <button class="counter__inc-button" @click="count++">INCREMENT</button>
    <button class="counter__reset-button" @click="count=0">RESET</button>
    <button class="counter__test-button" @click="onTestBtnClick">TEST</button>
  </div>
</template>

<script>
export default {
  name: 'MyComp',
  data() {
    return {
      count: this.startVal
      //count: 0
    }
  },
  props: {
    startVal: Number
  },
  methods: {
    incCount() {
      this.count++
    },
    resetCount() {
      this.count = 0;
    },
    onIncBtnClick(e) {
      //console.log(e)
      e.preventDefault()
      this.incCount()
    },
    onRstBtnClick(e) {
      //console.log(e)
      e.preventDefault()
      this.resetCount()
    },
    onTestBtnClick(e) {
      // console.log(e)
      e.preventDefault()
      this.$emit("test-btn-click", 'this is a string that was sent from MyComp');
    }
  },
  created() {
    //this.$emit("emitted-event")
  }
}
</script>

<style lang="scss">
  .counter {
    display: flex;
    align-items: center;
    flex-direction: column;
    padding: 50px;
    border: 2px solid blue;
    max-width: 300px;
    border-radius: 10px;

    &__heading, &__count {
      font-family: 'Segoe UI', Roboto, 'Open Sans', sans-serif;
    }

    button {
      padding: 5px;
      margin: 0 0 10px 0
    }
  }
</style>