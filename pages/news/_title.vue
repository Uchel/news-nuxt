<!-- pages/news/_title.vue -->
<template>
  <div>
    <h1>{{ title }}</h1>
    <img :src="img" :alt="title" />
    <p>{{ description }}</p>
  </div>
</template>

<script>
export default {
  // eslint-disable-next-line require-await
  async asyncData({ params, query }) {
    return {
      title: decodeURI(params.title),
      img: query.img,
      description: query.description,
    };
  },
};
</script>
