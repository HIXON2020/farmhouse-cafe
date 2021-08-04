<template>
  <layout-wrapper>
    <layout-visual title="get our latest infomation" :height="60" visual="visual-article"/>
    <div class="w-full md:max-w-3xl mx-auto pt-20">
      <h2 class="text-1 pb-5 border-gray-500 border-solid font-bold">{{item.title}}</h2>
      <div class="pt-4 mb-4">
        <time class="text-gray-700 text-base">{{item.date}}</time>
      </div>
      <div class="mb-20" v-html="item.body">
      </div>
      <base-button name="お知らせ一覧に戻る" link="/info/"></base-button>
    </div>
  </layout-wrapper>
</template>

<script>
import axios from 'axios'
export default {
  async asyncData({ $config, params, error }){
    try{
      const { data } = await axios.get(
        `${$config.apiUrl}/info/${params.id}`, {
        headers: {'X-API-KEY': $config.apiKey}
      })
      return {
        item: data
      }
    } catch(err){
      error({
        errorCode: 404
      })
    }
  },
  head(){
    return{
      title: this.item.title
    }
  }
}
</script>