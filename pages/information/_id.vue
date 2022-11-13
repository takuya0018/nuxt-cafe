<template>
  <main class="main">
    <h1 class="title">{{ title }}</h1>
    <p class="publishedAt">{{ publishedAt }}</p>
    <div class="post" v-html="body"></div>
  </main>
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