<template lang="pug">
  v-layout(column justify-center align-center)
    v-flex(xs12 sm8 md6)
      div.text-xs-center.section
        div.headline あなたが反応できるフレーム数は.....
        div.display-2 {{ vf }}F!#[span.vs-sec ({{ vs }}秒)]
        div.headline {{ showText(vf) }}

        a.twitter-share-button(
          href="https://twitter.com/share?ref_src=twsrc%5Etfw"
          data-show-count="true"
          :data-text="'あなたの視認可能フレームは' + vf + 'です！' + showText(vf) + ' | 視認可能フレーム計測ツール'"
          data-size="large"
          data-lang="ja"
          data-url="https://silly-hawking-704109.netlify.com"
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

<script>
import BigNumber from 'bignumber.js'

export default {
  data() {
    var vf = new BigNumber(this.$route.query.vf).toFixed(0)
    var vs = new BigNumber(this.$route.query.vs).toFixed(2)
    return {
      vf: vf,
      vs: vs
    }
  },
  methods: {
    round: function (num, digit) {
      return new BigNumber(num).toFixed(digit)
    },
    showText: function (vf) {
      if (vf < 10) {
        return "リトルマックの上スマ以上";
      }
      if (11 < vf && vf < 14) {
        return "ルキナの上スマ";
      }
      switch(true) {
        case vf == 15:
          return "インクリングのローラー";
          break;
        case vf == 16:
          return "リンクの横強";
          break;
        case vf == 17:
          return "サムスの最速NB";
          break;
        case vf == 18:
          return "ダークサムスの空下";
          break;
        case vf == 19:
          return "シークの下B";
          break;
        case vf == 20:
          return "ピットの空中横B";
          break;
        case vf == 21:
          return "ガノンの上スマ";
          break;
        case vf == 22:
          return "Wii Fitトレーナーの最速太陽礼拝";
          break;
        case vf == 23:
          return "シュルクの横B";
          break;
        case vf == 24:
          return "パックンフラワーの最速毒ブレス";
          break;
        case 24 < vf && vf < 30:
          return "しずえの釣り竿に反応できないかも！";
          break;
        case 29 < vf && vf < 40:
          return "ガオガエンのラリアットにモロ捕まります！";
          break;
        case 39 < vf && vf < 50:
          return "ジョーカーのエイハにギリ当たるかも";
          break;
        case 49 < vf && vf < 53:
          return "ゼルダの最速横B炎に反応できないかも";
          break;
        case 52 < vf && vf < 70:
          return "ガノンドロフの上強に反応できないかも！";
          break;
        default:
          return "目が疲れています！コントローラーを置いて休憩しましょう！";
          break;
      }
    }
  }
}
</script>
