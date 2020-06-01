<template>
  <li>
    <span>{{ video.snippet.title }}</span>
  </li>
</template>

<script>
export default {
  name: 'VideoListItem',
  props: ['video'],
};
</script>
