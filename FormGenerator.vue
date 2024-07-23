<template>
  <q-btn :label="text" type="submit" />
</template>

<script>
export default {
  name: 'FormGenerator',
  props: {
    text: {
      type: String,
      required: true
    }
  }
};
</script>
