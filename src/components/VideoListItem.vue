<template>
  <li class="list-group-item media" @click="onVideoSelect">
    <img class="mr-3" :src="url" />
    <div class="media-body">{{title}}</div>
  </li>
</template>

<script>
export default {
  name: "VideoList",
  props: {
    video: Object
  },
  computed: {
    url() {
      return this.video.snippet.thumbnails.default.url;
    },
    title() {
      return this.video.snippet.title;
    }
  },
  methods: {
    onVideoSelect() {
      this.$emit("videoSelect", this.video);
    }
  }
};
</script>

<style scoped>
li {
  display: flex;
  cursor: pointer;
}
</style>
