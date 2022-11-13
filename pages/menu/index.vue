<template>
  <layout-wrapper>
    <layout-visual title="Menu" :height="40" visual="visual-menu" />
    <div class="w-full md:max-w-3xl mx-auto pt-20 px-6 md:px-0">
      <div class="mb-20">
        <layout-menu-list
          v-for="(item, index) in contents"
          :key="index"
          :image="item.image"
          :image-url="item.image.url"
          :name="item.name"
          :body="item.body"
          :price="item.price"
        />
      </div>
      <base-button name="トップへ戻る" link="/" />
    </div>
  </layout-wrapper>
</template>

<script>
import axios from 'axios'
import LayoutMenuList from '../../components/LayoutMenuList.vue'
export default {
  name: 'MenuIndex',
  components: { LayoutMenuList },
  async asyncData() {
    const { data } = await axios.get(
      `${process.env.API_URL}/menu/`,
      {
        headers:{'X-MICROCMS-API-KEY': process.env.API_KEY }
      }
    )
    return data
  },
  head() {
    return {
      title: 'メニュー',
    }
  },
}
</script>


<style>
.visual-home {
  background-image: url('~@/assets/img/visual-home.jpg');
}
</style>