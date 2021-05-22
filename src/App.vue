<template>
  <div class="container">
      <MyComp 
        startVal=999
        @test-btn-click="testBtnClick"
      />
      <p>Current count={{ setVal }}</p>
  </div>
</template>

<script>
import MyComp from '@/components/MyComp.vue'

export default {
  name: 'App',
  components: {
    MyComp
  },
  data() {
    return {
      mystring: ''
    }
  },
  // only runs if values are changed (cached); no properties allowed
  computed: {
    setVal() {
      return this.mystring
    }
  },
  // 
  methods: {
    testBtnClick(return_val) {  // value sent from MyComp as @test-btn-click
      this.mystring = return_val
    }
  }
}
</script>

<style lang="scss">
  .container {
    display: flex;
    align-items: center;
    flex-direction: column;
  }
</style>
