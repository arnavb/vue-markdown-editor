<template>
  <div class="col" v-html="markdownToHtml"></div>
</template>

<script>
import marked from 'marked';
import DOMPurify from 'dompurify';

export default {
  name: 'OutputPanel',
  props: {
    markdownContent: {
      type: String,
      required: true,
    },
  },
  computed: {
    markdownToHtml() {
      return DOMPurify.sanitize(marked(this.markdownContent, { gfm: true }));
    },
  },
};
</script>

<style scoped></style>
