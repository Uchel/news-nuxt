<template>
  <div class="news-card">
    <nuxt-link
      :to="{
        name: 'news-detail', // Nama rute yang sesuai dengan halaman detail berita
        params: { title: encodeURI(title) }, // Parameter dalam path
        query: { img: srcImg, description: description }, // Query parameters
      }"
    >
      <img :src="srcImg" :alt="altImg" />
      <h3>{{ title }}</h3>
      <p>{{ description }}</p>
    </nuxt-link>
  </div>
</template>

<script>
export default {
  props: {
    srcImg: {
      type: String,
      default: '',
    },
    altImg: {
      type: String,
      default: '',
    },
    title: {
      type: String,
      default: '',
    },
    description: {
      type: String,
      default: '',
    },
  },
}
</script>

<style lang="scss" src="../assets/css/component/uni.scss"></style>
