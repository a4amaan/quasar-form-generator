<template>
  <div>
    <div v-for="field in schema.fields" :key="field.model">
      <q-input v-if="field.type === 'text'" v-model="formData[field.model]" :label="field.label" :dense="field.dense"
        :outlined="field.outlined" :disable="field.disable" :readonly="field.readonly" :label-color="field.labelColor"
        :color="field.color" :bg-color="field.bgColor" :dark="field.dark" :filled="field.filled"
        :borderless="field.borderless" :standout="field.standout" :hide-bottom-space="field.hideBottomSpace"
        :rounded="field.rounded" :square="field.square" :item-aligned="field.itemAligned"
        :input-class="field.inputClass" :input-style="field.inputStyle" :debounce="field.debounce"
        :maxlength="field.maxlength" :error-message="field.errorMessages" :no-error-icon="field.noErrorIcon"
        :stack-label="field.stackLabel" :hint="field.hint" :name="field.name" :mask="field.mask"
        :fill-mask="field.fillMask" :reverse-fill-mask="field.reverseFillMask" :unmasked-value="field.unmaskedValue"
        :error="field.error" :reactive-rules="field.reactiveRules" :lazy-rules="field.lazyRules"
        :loading="field.loading" :clearable="field.clearable" :autofocus="field.autofocus" :for="field.for">
        <template v-if="field.leftIcon" v-slot:prepend>
          <q-icon :name="field.leftIcon" />
        </template>
        <template v-if="field.rightIcon" v-slot:append>
          <q-icon :name="field.rightIcon" />
        </template>
        <template v-if="field.beforeInput" v-slot:before>
          <div>{{ field.beforeInput }}</div>
        </template>
        <template v-if="field.afterInput" v-slot:after>
          <div>{{ field.afterInput }}</div>
        </template>
      </q-input>

      <q-select v-if="field.type === 'select'" v-model="formData[field.model]" :label="field.label"
        :square="field.square" :stack-label="field.stackLabel" :options="field.values" :option-label="field.optionLabel"
        :option-disable="field.optionDisable" :hide-hint="field.hideHint" :prefix="field.prefix" :suffix="field.suffix" :options-dense="field.optionsDense"
        :new-value-mode="field.newValueMode" :options-dark="field.optionsDark"
        :options-selected-class="field.optionsSelectedClass" :autocomplete="field.autocomplete"
        :bottom-slots="field.bottomSlots" :hide-dropdown-icon="field.hideDropdownIcon" :clearable="field.clearable"
        :fill-input="field.fillInput" :transition-show="field.transitionShow" :lazy-rules="field.lazyRules"
        :hint="field.hint" :dense="field.dense" :outlined="field.outlined"
        :transition-duration="field.transitionDuration" :transition-hide="field.transitionHide"
        :use-input="field.useInput" :disable="field.disable" :readonly="field.readonly" :behavior="field.behavior"
        :label-color="field.labelColor" :error="field.error" :reactive-rules="field.reactiveRules"
        :autofocus="field.autofocus" :for="field.for" :maxlength="field.maxlength" :input-debounce="field.inputDebounce"
        :input-style="field.inputStyle" :debounce="field.debounce" :color="field.color" :bg-color="field.bgColor"
        :name="field.name" :virtual-scroll-horizontal="field.virtualScrollHorizontal" :dark="field.dark"
        :filled="field.filled" :borderless="field.borderless" :standout="field.standout"
        :hide-bottom-space="field.hideBottomSpace" :rounded="field.rounded" :input-class="field.inputClass"
        :multiple="field.multiple" :display-value="field.displayValue" :display-value-html="field.displayValueHtml"
        :hide-selected="field.hideSelected" :max-values="field.maxValues" :menu-anchor="field.menuAnchor"
        :menu-self="field.menuSelf" :menu-offset="field.menuOffset" :options-html="field.optionsHtml"
        :options-cover="field.optionsCover" :menu-shrink="field.menuShrink" :map-options="field.mapOptions"
        :emit-value="field.emitValue" :tabindex="field.tabindex" :table-colspan="field.tableColspan"
        :error-message="field.errorMessage" :no-error-icon="field.noErrorIcon">
      </q-select>

      <q-radio v-if="field.type === 'radio'" v-model="formData[field.model]" :val="field.val" :label="field.label" />
    </div>
  </div>
</template>

<script>

export default {
  props: {
    schema: Object,
    formData: Object
  },
  data() {
    return {
    }
  },
  methods: {
  }
}
</script>
