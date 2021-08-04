<template>
  <layout-wrapper>
    <layout-visual title="店舗情報" :height="50 " visual="visual-shop" />
    <div class="container md:max-w-4xl mx-auto pt-20 pb-20 px-6 md:px-0">
      <table class="table-auto w-full mb-10">
        <tbody>
          <tr>
            <td class="border px-4 py-2">店舗名</td>
            <td class="border px-4 py-2">Farmhouse Cafe</td>
          </tr>
          <tr>
            <td class="border px-4 py-2">店舗住所</td>
            <td class="border px-4 py-2">787-0310 高知県土佐清水市浦尻5-11</td>
          </tr>
          <tr>
            <td class="border px-4 py-2">座席数</td>
            <td class="border px-4 py-2">8席</td>
          </tr>
        </tbody>
      </table>
      <div class="mb-10">
        <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3354.4246495493026!2d132.968182214461!3d32.780997880970816!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x354f33daae4a048d%3A0x9a8881f6bdfc0bfd!2z44CSNzg3LTAzMTAg6auY55-l55yM5Zyf5L2Q5riF5rC05biC5rWm5bC777yV4oiS77yR77yR!5e0!3m2!1sja!2sjp!4v1627783142921!5m2!1sja!2sjp" class="w-full" height="450" style="border:0;" allowfullscreen="" loading="lazy"></iframe>
      </div>
      <div class="mx-auto mb-10 text-center">
        <nuxt-link to="/" class="rounded-lg px-4 md:px-4 py-3 md:py-4 xl:py-3 bg-white hover:bg-gray-200 md:text-lg xl:text-base text-gray-800 fnt-semibold leadng-tight shadow-md">トップへ戻る</nuxt-link>
      </div>
    </div>
  </layout-wrapper>
</template>

<script>
export default {
  head(){
    return {
      title: '店舗情報'
    }
  }
}
</script>