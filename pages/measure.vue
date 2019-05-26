<template lang="pug">
  v-layout(column justify-center align-center)
    v-flex(xs12 sm8 md6)
      div.text-xs-center.section
        h1 CountDown:
          vac(:end-time="new Date().getTime() + 4000")
            span(slot="process" slot-scope="{ timeObj }") {{ timeObj.s}}
            span(slot="finish") 計測中......

        v-img(v-if="isCounting" src="/smashball_blank.png" width="300px" height="300px")
        v-img(v-if="!isCounting" src="/smashball.png" width="300px" height="300px")

        v-btn(v-if="isCounting" disable) Push!
        v-btn(v-else v-on:click="stopTimer()") Push!
</template>

<style>
.section {
  position: absolute;
  top: 0px;
  right: 0px;
  bottom: 0px;
  left: 0px;
  margin: auto;

  width: 100%;
  height: 50%;
}
</style>

<script>
export default {
  data() {
    return {
      count: 3,
      isCounting: true,
      isStop: false,
      startTime: Date.now(),
      endTime: Date.now()
    }
  },
  mounted() {
    var countDown = 4000
    var min = 2
    var max = 5
    var randCount = Math.floor( Math.random() * (max + 1 - min) ) + min
    var timeout = countDown + randCount*1000
    setTimeout(() => {
      this.isCounting = false
      this.startTime = Date.now()
    }, timeout)
  },
  methods: {
    stopTimer: function () {
      this.endTime = Date.now()
      this.isStop = true
      var visibleFrame =  (this.endTime - this.startTime)/15
      var visibleSec =  (this.endTime - this.startTime)/1000
      this.$router.push('/result?vf=' + visibleFrame + '&vs=' + visibleSec)
    }
  }
}
</script>
