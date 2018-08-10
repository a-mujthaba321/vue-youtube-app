<template>
  <div>{{ video.snippet.title }}</div>
</template>

<script>
export default {
  name: "VideoDetail",
  props: {
    videos: Object
  }
};
</script>

<style scoped>
</style>
