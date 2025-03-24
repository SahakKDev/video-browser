<template>
  <li class="list-group-item d-flex" @click="onVideoSelect">
    <div class="flex-shrink-0">
      <img :src="thumbnailUrl" alt="thumbnail image" />
    </div>
    <div class="flex-grow-1 ms-3">
      <h3>{{ video.snippet.channelTitle }}</h3>
      {{ video.snippet.title }}
    </div>
  </li>
</template>

<script>
export default {
  name: "VideoListItem",
  props: ["video"],
  methods: {
    onVideoSelect() {
      this.$emit("videoSelect", this.video);
    },
  },
  computed: {
    thumbnailUrl() {
      return this.video.snippet.thumbnails.default.url;
    },
  },
};
</script>

<style>
li {
  cursor: pointer;
}

li:hover {
  background-color: #eee;
}
</style>
