<template>
  <textarea
    class="col"
    :value="value"
    @input="$emit('input', $event.target.value)"
  ></textarea>
</template>

<script>
export default {
  name: 'Editor',
  props: {
    value: {
      type: String,
      required: true,
    },
  },
};
</script>

<style scoped>
textarea {
  resize: none;
  margin: 5px;
  padding: 8px;
  font-family: 'Roboto Mono', Arial, Helvetica, sans-serif;
  font-size: 14px;
}
</style>
