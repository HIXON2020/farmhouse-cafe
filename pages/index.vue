<template>
  <layout-wrapper>
    <layout-visual 
    title="Live with favorite things."
    message="お知らせやメニューをmicroCMSを導入したDEMoサイトになります。"
     />
    <div class="w-full md:max-w-3xl mx-auto pt-20 px-6 md:px-0">

      <!-- メニューやおすすめ商品等ピックアップ -->
      <base-heading>Farmhouse Cafeおすすめのアイテム</base-heading>
      <div class="flex md:flex-wrap justify-between mb-20 md:mb-0">
        <layout-items-list
          v-for="(item,index) in threeItems"
          :key="index"
          :image="item.image"
          :image-url="item.image.url"
          :name="item.name"
          :body="item.body"
          :price="item.price"
          item-class="md:w-56 mb-20 shadow-lg bg-gray-100"
          block-class="max-w"
          image-class="w-full"
          data-class="px-6 py-4"
          :flag-body="false"
        >
        </layout-items-list>
      </div>
      <base-button name="商品一覧" link="/items/"></base-button>
      <!-- メニューやおすすめ商品等ピックアップここまで -->


      <!-- お知らせ -->
      <base-heading>お知らせ＆最新情報</base-heading>
      <div class="mb-10">
        <layout-info-list
          v-for="(item,index) in infoItems"
          :id="item.id"
          :key="index"
          :date="item.date"
          :title="item.title"
        ></layout-info-list>`
      </div>
      <!-- お知らせここまで -->
      <base-button name="他のお知らせ" link="/info/" />
    </div>
  </layout-wrapper>
</template>

<script>
import axios from 'axios'

import BaseButton from '~/components/BaseButton.vue';
import BaseHeading from '~/components/BaseHeading.vue';
import LayoutInfoList from '~/components/LayoutInfoList.vue';
import LayoutItemsList from '~/components/LayoutItemsList.vue';
import LayoutVisual from '~/components/LayoutVisual.vue';
import LayoutWrapper from '~/components/LayoutWrapper.vue';

export default{
  components: { LayoutWrapper, LayoutVisual, BaseHeading, BaseButton, LayoutItemsList, LayoutInfoList },

  async asyncData({ $config }){
    const goods = await axios.get(
      `${$config.apiUrl}/goods?limit=3&filters=flag[equals]true`, {
        headers: {'X-API-KEY': $config.apiKey}
    })
    const info = await axios.get(
      `${$config.apiUrl}/info?limit=3`, {
        headers: {'X-API-KEY': $config.apiKey}
    })

    return {
      threeItems: goods.data.contents,
      infoItems: info.data.contents,
    }
  },
  
}

</script>

<style>
  
</style>
