<template lang="pug">
  v-layout(column justify-center align-center)
    v-flex(xs12 sm8 md6)
      div.text-xs-center.section
        div 何フレームまで反応できる？
        div 視認可能フレーム計測ツール
        div.headline FrameMeasure

        v-btn(to="/howtouse") 計測する
</template>

<style>
.section {
  height: 50%;
}
</style>

<script>
import Logo from '~/components/Logo.vue'
import VuetifyLogo from '~/components/VuetifyLogo.vue'

export default {
  components: {
    Logo,
    VuetifyLogo
  }
}
</script>
