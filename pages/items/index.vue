<template>
  <layout-wrapper>
    <layout-visual title="Enjoy Your Shopping" :height="70" visual="visual-items"/>
    <div class="container md:max-w-4xl mx-auto pb-20 pt-20 px-6 md:px-0">
      <base-heading>商品一覧</base-heading>
      <!-- カード -->
      <div class="mb-20">
        <layout-items-list
          v-for="(item,index) in items"
          :key="index"
          :image="item.image"
          :image-url="item.image.url"
          :name="item.name"
          :body="item.body"
          :price="item.price"
        ></layout-items-list>
      </div>
        <!-- カード -->
      <base-button name="トップへ戻る" link="/"></base-button>
    </div>
  </layout-wrapper>
</template>

<script>
import axios from 'axios'
export default {
  async asyncData({ $config }){
    const { data } = await axios.get(`${$config.apiUrl}/goods`, {
      headers: {'X-API-KEY': $config.apiKey}
    })
    return {
      items: data.contents,
    }
  },
  head(){
    return {
      title: '商品ページ'
    }
  }
}
</script>