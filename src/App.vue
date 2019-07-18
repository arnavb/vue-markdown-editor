<template>
  <div id="app">
    <Editor v-model="rawMarkdown" />
    <OutputPanel :markdown-content="rawMarkdown" />
  </div>
</template>

<script>
import Editor from './components/Editor.vue';
import OutputPanel from './components/OutputPanel.vue';

export default {
  name: 'App',

  data() {
    return {
      rawMarkdown: '',
    };
  },

  components: {
    Editor,
    OutputPanel,
  },
};
</script>

<style>
*,
*::before,
*::after {
  box-sizing: border-box;
}

html,
body {
  margin: 0;
  padding: 0;
  height: 100vh;
  width: 100%;
}

#app {
  height: 100%;
  width: 100%;
  display: flex;
}

.col {
  flex: 1;
  border: 1px solid black;
  overflow: auto;
}
</style>
