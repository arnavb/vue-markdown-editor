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

  components: {
    Editor,
    OutputPanel,
  },

  data() {
    return {
      rawMarkdown: '',
    };
  },
};
</script>

<style>
@import url('https://fonts.googleapis.com/css?family=Roboto&display=swap');
@import url('https://fonts.googleapis.com/css?family=Roboto+Mono&display=swap');

*,
*::before,
*::after {
  box-sizing: border-box;
  /* margin: 0;
  padding: 0; */
}

html,
body {
  height: 100vh;
  width: 100%;
  margin: 0;
  padding: 0;
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

@media (max-width: 768px) {
  #app {
    display: block;
  }

  .col {
    width: 100%;
    height: 50%;
  }
}

/* Styles for rendered markdown code*/
h1,
h2,
h3,
h4,
h5,
h6,
p,
li,
pre,
code {
  font-family: 'Roboto', Arial, Helvetica, sans-serif;
}

pre {
  background-color: lightgrey;
  color: white;
  padding: 5px;
  overflow-x: scroll;
}
</style>
