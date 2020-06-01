<template>
  <ul>
    Video list contains
    {{
      videos.length
    }}
  </ul>
</template>

<script>
export default {
  name: 'VideoList',
  props: {
    videos: Array,
  },
};
</script>

<style scoped></style>
