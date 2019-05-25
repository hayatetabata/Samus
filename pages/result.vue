<template lang="pug">
  v-layout(column justify-center align-center)
    v-flex(xs12 sm8 md6)
      div.text-xs-center.section
        div あなたの反応可能フレーム数は.....
        div.headline 約24F!#[span (0.36秒)]
        div インクリングのローラーに反応できません！残念！

        v-btn Twitterでシェアする
        v-btn(to="/") トップに戻る
</template>
