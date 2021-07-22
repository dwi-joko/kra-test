<template>
  <!-- <div class="banner"><img class="w-full mt-2 rounded" :src="article.image" height="140" width="210" /></div> -->

  <div class="page-wrapper">
    <div class="banner">
      <img src="../assets/banner.jpeg" alt="" />
    </div>

    <p>test</p>
    <h3>{{ article.title }}</h3>
  </div>
</template>

<script>
export default {
  props: {
    article: {
      type: Object,
      required: true,
    },
  },
  data() {
    return {};
  },
};
</script>
