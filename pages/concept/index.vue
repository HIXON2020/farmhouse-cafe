<template>
  <layout-wrapper>
    <layout-visual title="About Farmhouse Cafe" :height="65 " visual="visual-concept"/>
    <div class="container w-full mx-auto pt-20 pb-20 px-6 md:px-0">
      <h3 class="text-2xl text-yellow-800 font-extrabold mb-10 text-center">
        暮らしをシンプルに。<br>顔の見える生産者。
      </h3>
      <div class="md:max-w-4xl md:flex mx-auto flex justify-between md:items-center p-4 mb-10">
        <div>
          <p class="mb-5">
            つくる人の優しい想いが伝わるアイテムを集めています。<br>
            オーガニックで身体に優しいモノをお届けしております。<br>
            毎日使うものだからこそ、気持ち良く安心に使いたい。<br>
            そう考えるようになって、出会ったアイテムたちです。<br>
            そしてひとつひとつにストーリーがあります。<br>
            そのストーリーもひとつのお楽しみ。<br>
            ＊どうやってつくられているのか？<br>
            ＊なぜこの素材なのか？<br>
            ご使用上でご不明な点などは、お気軽にお問い合わせくださいね。<br>
            心が豊かになり身体が喜ぶものばかり。<br>
            自信をもってお届けします。
          </p>
        </div>
        <img class="float-right ml-4 my-2 h-56" src="~/static/image3.jpeg" />
      </div>
    </div>
    <base-button name="トップへ戻る" link="/"></base-button>
  </layout-wrapper>
</template>

<script>
export default {
  head(){
    return {
      title: 'コンセプト'
    }
  }
}
</script>