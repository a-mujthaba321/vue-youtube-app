<template>
  <ul class="list-group col-md-4">
    <VideoItem 
      v-for="video in videos"
      :video="video"
      :key="video.etag"
      @videoSelect="onVideoSelect"
    />
  </ul> 
</template>


<script>
import VideoItem from "./VideoItem";
export default {
  name: "VideoList",
  components: { VideoItem },
  props: {
    videos: Array
  },
  methods: {
    onVideoSelect(video) {
      this.$emit("videoChange", video);
    }
  }
};
</script>


<style>
</style>
