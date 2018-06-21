<template>
  <div>
    <div class="list">
      <!-- 这里是touchstart，没有大写 -->
      <div 
        @click="handleLettersClick" 
        class="list-item" 
        v-for="item of letters"
        @touchstart="handleTouchStart"
        @touchmove="handleTouchMove"
        @touchend="handleTouchEnd"
        :ref="item"
        >
        {{item}}
      </div>
    </div>  
  </div>
</template>

<script>

export default {
  name: 'CityAlphabet',
  props: {
    cities: Object
  },
  data (){
    return {
      touchStatus: false,
      startY: '',
      timer: null
    }
  },
  updated (){
    this.startY = this.$refs['A'][0].offsetTop
  },
  methods: {
    handleLettersClick (e){
      this.$emit('change',e.target.innerText)
    },
    handleTouchStart (){
      this.touchStatus = true
    },
    handleTouchMove (e){
      if(this.touchStatus){
        if(this.timmer){
          clearTimeout(this.timer)
        }
        this.timer = setTimeout(() => {
                    //$refs['A']是一个数组，不是dom。这个数组的第一个才是dom
            const touchY = e.touches[0].clientY -this.startY - 84,
                  index = Math.floor(touchY/22)
            if(index >= 0 && index < this.letters.length){
              //只能绑定在该组件上，
              // this.$emit('change',this.letters[index])
              //因为这里出发的事件和上面的change一样功能，所以两次都是一样向外触发change事件
              this.$emit('change',this.letters[index])
            }   
          },16)
      }
    },
    handleTouchEnd (){
      this.touchStatus = false
    }
  },
  computed: {
    letters (){
      const letters = []
      for (var i in this.cities) {
        letters.push(i)
      }
      // 忘记return
      return letters
    }
  }
}
</script>
<style lang="stylus" scoped>
@import '~styles/varible.styl'
  .list
    display: flex
    flex-direction: column
    justify-content: center
    position: absolute
    top: 1.5rem
    right: 0
    bottom: 0
    width: .4rem
    .list-item
      line-height: .44rem
      text-align: center
      color: $bgcolor
</style>
