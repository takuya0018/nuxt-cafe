<!-- eslint-disable vue/no-v-html -->
<template>
  <layout-wrapper>
    <layout-visual
      title="Information"
      :height="40"
      visual="visual-information"
    />

    <div class="w-full md:max-w-3xl mx-auto pt-20 px-6 md:px-0">
      <h2 class="text-xl pb-5 border-b border-gray-500 border-solid font-bold">
        {{ title }}
      </h2>
      <div class="pt-4 mb-4">
        <time class="text-gray-700 text-base">{{ date | formatDate }}</time>
      </div>
      <div class="mb-20" v-html="body"></div>
      <base-button name="お知らせへ戻る" link="/information/" />
    </div>
  </layout-wrapper>
</template>

<script>
import axios from 'axios'

export default {
  async asyncData({ $config,params }) {
    const { data } = await axios.get(
      `https://cafe-news.microcms.io/api/v1/information/${params.id}`,
      {
        headers: { 'X-MICROCMS-API-KEY': $config.apiKey }
      }
    )
    return data
  }
}
</script>