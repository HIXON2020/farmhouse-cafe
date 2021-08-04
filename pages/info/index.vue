<template>
  <layout-wrapper>
    <layout-visual title="infomation" :height="70" visual="visual-info" />
    <div class="container md:max-w-4xl mx-auto pb-20 pt-20 px-6 md:px-0">
      <div class="mb-10">
        <layout-info-list
        v-for="(item,index) in items"
        :id="item.id"
        :key="index"
        :date="item.date"
        :title="item.title"
        ></layout-info-list>
      </div>
      <base-button name="トップへ戻る" link="/"></base-button>
    </div>
  </layout-wrapper>
</template>

<script>
import axios from 'axios'

export default {
  async asyncData({ $config }){
    const { data } = await axios.get(
      `${$config.apiUrl}/info`,{
      headers: { 'X-API-KEY': $config.apiKey },
    })
    return {
      items: data.contents,
    }
  },
  head(){
    return {
      title: 'お知らせ'
    }
  }
}
</script>