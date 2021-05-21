<template>
  <div class="container">
      <MyComp 
        startVal=5 
        @test-btn-click="testBtnCLick"
      />
      
  </div>
</template>

<script>
import MyComp from '@/components/MyComp.vue'

export default {
  name: 'App',
  components: {
    MyComp
  },
  methods: {
    testBtnCLick() {
      console.log('test')
    }
  }
}
</script>

<style lang="scss">
  .container {
    display: flex;
    justify-content: center;
  }
</style>
