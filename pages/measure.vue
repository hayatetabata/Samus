<template lang="pug">
  v-layout(column justify-center align-center)
    v-flex(xs12 sm8 md6)
      div.text-xs-center.section
        h1 CountDown:
          // 101 seconds
          vac(:end-time="new Date().getTime() + 4000")
            span(slot="process" slot-scope="{ timeObj }") {{ timeObj.s}}
            span(slot="finish") Measuring....

        v-img(v-if="!showBall" src="/smashball_blank.png" width="300px" height="300px")
        v-img(v-if="showBall" src="/smashball.png" width="300px" height="300px")

        v-btn(v-on:click="stopTimer()") Push!

        div(v-if="isStop") {{ (endTime - startTime)/15 }}
        div(v-if="isStop") {{ (endTime - startTime)/1000 }}
</template>

<script>
export default {
  data() {
    return {
      count: 3,
      showBall: false,
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
      this.showBall = true
      this.startTime = Date.now()
    }, timeout)
  },
  methods: {
    stopTimer: function () {
      this.endTime = Date.now()
      this.isStop = true
    }
  }
}
</script>
