<template>
  <!-- eslint-disable-next-line vue/no-v-html -->
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

  computed: {
    convertedMarkdown() {
      return this.md.render(this.markdownContent);
    },
  },

  created() {
    this.md = new MarkdownIt();
  },
};
</script>

<style scoped></style>
