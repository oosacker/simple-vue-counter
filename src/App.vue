<template>
  <div class="container">
      <MyComp 
        startVal=5 
        @test-btn-click="testBtnClick"
      />
      <p>{{ setVal }}</p>
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
    testBtnClick(return_val) {
      // console.log('test')
      console.log(return_val)
      this.mystring = return_val
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
