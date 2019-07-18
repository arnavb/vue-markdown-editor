<template>
  <div class="col" v-html="convertedMarkdown"></div>
</template>

<script>
import MarkdownIt from 'markdown-it';

export default {
  name: 'OutputPanel',

  props: {
    markdownContent: {
      type: String,
      required: true,
    },
  },

  created() {
    this.md = new MarkdownIt();
  },

  computed: {
    convertedMarkdown() {
      return this.md.render(this.markdownContent);
    },
  },
};
</script>

<style scoped></style>
