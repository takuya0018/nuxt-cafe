<template>
  <layout-wrapper>
    <layout-visual
      title="Information"
      :height="40"
      visual="visual-information"
    />
    <div class="w-full md:max-w-3xl mx-auto pt-20 px-6 md:px-0">
      <layout-infomation-list
        v-for="(item, index) in infoList"
        :id="item.id"
        :key="index"
        :date="item.date"
        :title="item.title"
        />
      <base-button name="トップへ戻る" link="/" />
    </div>
  </layout-wrapper>
</template>

<script>
import axios from 'axios'
export default {
  name: 'InformationIndex',
  // async asyncData({ $microcms }) {
  //   const data = await $microcms.get({
  //     endpoint: 'information',
  //     queries: { limit: 20, filters: 'createdAt[greater_than]2021' },
  //   })
  //   return data
  // },
  async asyncData() {
    const { data } = await axios.get(
      `${process.env.API_URL}/information/`,
      {
        headers:{'X-MICROCMS-API-KEY': process.env.API_KEY }
      }
    )
    return {
      infoList: data.contents
    }
  },
  head() {
    return {
      title: 'お知らせ',
    }
  },
}
</script>
