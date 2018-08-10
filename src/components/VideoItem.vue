<template>
  <li class="list-group-item media">
    <img 
      :src="thumbnailUrl" 
      class="mr-3">
    <div class="media-body">
      {{ video.snippet.title }} 
    </div>
  </li>
</template>

<script>
export default {
  name: "VideoItem",
  props: {
    video: Object
  },
  computed: {
    thumbnailUrl() {
      return this.video.snippet.thumbnails.default.url;
    }
  }
};
</script>

<style scoped>
li {
  display: flex;
  cursor: pointer;
}

li:hover {
  background-color: rgba(228, 228, 228, 0.637);
}
</style>
