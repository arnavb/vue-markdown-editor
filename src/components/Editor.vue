<template>
  <textarea
    class="col"
    :value="content"
    @input="$emit('input', $event.target.value)"
  ></textarea>
</template>

<script>
export default {
  name: 'Editor',

  data() {
    return {
      content: '',
    };
  },
};
</script>

<style scoped>
textarea {
  resize: none;
  margin: 0;
}
</style>
