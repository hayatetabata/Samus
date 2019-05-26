<template lang="pug">
  v-layout(column justify-center align-center)
    v-flex(xs12 sm8 md6)
      div.text-xs-center.section
        div 赤いスマッシュロゴが見えたら
        v-img(src="/smashball.png")
        div 下のPushボタンを押そう！
        v-btn() push

        v-btn(to="/measure") Start!
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
