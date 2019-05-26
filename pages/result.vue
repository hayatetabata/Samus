<template lang="pug">
  v-layout(column justify-center align-center)
    v-flex(xs12 sm8 md6)
      div.text-xs-center.section
        div.headline あなたの反応可能フレーム数は.....
        div.display-2 {{ $route.query.vf }}F!#[span.vs-sec ({{ $route.query.vs }}秒)]
        div.headline インクリングのローラーに反応できません！残念！

        a.twitter-share-button(
          href="https://twitter.com/share?ref_src=twsrc%5Etfw"
          data-show-count="true"
          :data-text="'あなたの視認可能フレームは' + $route.query.vf + 'です！ | 視認可能フレーム計測ツール'"
          data-size="large"
          data-lang="ja"
          ) ツイート
        span で結果をシェア
        script(async src="https://platform.twitter.com/widgets.js" charset="utf-8")
        br
        v-btn(to="/") トップに戻る
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

.vs-sec {
  font-size: 15px;
}

.twitter-share-button {
  font-size: 30px;
}
</style>
