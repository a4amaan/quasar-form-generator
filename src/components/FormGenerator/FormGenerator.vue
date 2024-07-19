<template>
  <div>
    <q-form @submit="onSubmit">
      <component
        v-for="(field, index) in schema.fields"
        :key="index"
        :is="getComponent(field)"
        v-bind="field.props"
        v-model="formData[field.model]"
      />
      <q-btn type="submit" label="Submit" />
    </q-form>
  </div>
</template>

<script>
export default {
  name: 'FormGenerator',
  props: {
    schema: {
      type: Object,
      required: true
    }
  },
  data() {
    return {
      formData: {}
    };
  },
  methods: {
    getComponent(field) {
      // Map your schema field types to Quasar components
      const componentMap = {
        input: 'q-input',
        select: 'q-select',
        checkbox: 'q-checkbox',
        // Add more mappings as needed
      };
      return componentMap[field.type] || 'q-input';
    },
    onSubmit() {
      // Handle form submission
      this.$emit('submit', this.formData);
    }
  }
};
</script>
