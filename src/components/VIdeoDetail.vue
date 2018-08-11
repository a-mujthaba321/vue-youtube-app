</<template>
<div v-if="video.snippet" class="col-md-8">
  <div class="embed-responsive embed-responsive-16by9">
    <iframe width="560" height="315" :src="videoURL"/>
  </div>
  <div class="details">
    <h4>{{video.snippet.title}}</h4>
    <p>{{video.snippet.description}}</p>
  </div>
</div>
</template>

<script>
export default {
  name: "VideoDetail",
  props: {
    video: Object
  },
  computed: {
    videoURL() {
      const { videoId } = this.video.id;
      const embedURL = `https://www.youtube.com/embed/${videoId}`;
      return embedURL;
    }
  }
};
</script>
<style scoped>
.details {
  margin-top: 10px;
  padding: 10px;
  border: 1px solid #ddd;
}
</style>
