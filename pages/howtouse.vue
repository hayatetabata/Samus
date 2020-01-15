<template lang="pug">
  v-layout(column justify-center align-center)
    v-flex(xs12 sm8 md6)
      div.text-xs-center.section
        div 赤いスマッシュロゴが見えたら
        v-img(src="/smashball.png")
        div 下のPushボタンを押そう！
        v-btn() Push!

        v-btn(to="/measure") ルールがわかったので計測をする
</template>

<style>
.section {
  position: absolute;
  top: 0px;
  right: 0px;
  bottom: 0px;
  left: 0px;
  margin: 40px auto 0px;

  width: 300px;
  height: 50%;
}
</style>
