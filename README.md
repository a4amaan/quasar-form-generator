Here's a comprehensive README file for your `FormGenerator` component, detailing how to use it, including the various props like `dense`, `outlined`, `square`, etc.

---

# FormGenerator

The `FormGenerator` component is a versatile and dynamic form builder for Vue.js applications, using the Quasar Framework. It allows developers to define form schemas and generate forms automatically with rich features and customizable properties.

## Installation

To install the `FormGenerator` component, use npm:

```bash
npm install form-generator
```

## Usage

Import the `FormGenerator` component into your Vue component and define the form schema.

### Example

```vue
<template>
  <div class="q-pa-xl">
    <FormGenerator :schema="schema" :formData="formData" />
    <q-btn @click="submitForm">Submit</q-btn>
  </div>
</template>

<script>
import FormGenerator from 'form-generator';

export default {
  components: {
    FormGenerator
  },
  data() {
    return {
      formData: {},
      schema: {
        fields: [
          {
            type: 'text',
            label: 'First Name',
            model: 'firstName',
            dense: true,
            outlined: true,
            hint: "Required",
            rightIcon: "add",
            square: true,
            clearable: true,
          },
          {
            type: 'select',
            label: 'Gender',
            model: 'gender',
            values: ['Male', 'Female'],
            dense: true,
            outlined: true,
            hint: "Required",
            square: true,
            clearable: true,
            optionsDense: true
          },
          { label: "Male", type: "radio", model: "gender", val: "male" },
          { label: "Female", type: "radio", model: "gender", val: "female" },
        ]
      }
    }
  },
  methods: {
    submitForm() {
      console.log(this.formData);
    },
  }
}
</script>
```

## Schema Configuration

The `schema` object defines the fields and their properties in the form. Each field can be customized with various properties to control its appearance and behavior.

### Common Field Properties

- `type`: The type of input field (`text`, `select`, `radio`, etc.).
- `label`: The label for the field.
- `model`: The key in the `formData` object that stores the field's value.
- `dense`: Makes the field more compact.
- `outlined`: Adds an outline style to the field.
- `square`: Renders the field with square corners.
- `clearable`: Adds a clear button to the field.
- `hint`: Provides a hint or additional information about the field.
- `rightIcon`: Adds an icon to the right of the field.
- `options`: (For `select` and `radio` types) The options available in the select dropdown or radio group.

### Advanced Field Properties

- `disable`: Disables the field.
- `readonly`: Makes the field read-only.
- `labelColor`: Sets the color of the label.
- `color`: Sets the color of the input field.
- `bgColor`: Sets the background color of the field.
- `dark`: Applies a dark theme to the field.
- `filled`: Applies a filled style to the field.
- `borderless`: Removes the border from the field.
- `standout`: Highlights the field.
- `hideBottomSpace`: Hides the bottom space in the field.
- `rounded`: Applies rounded corners to the field.
- `itemAligned`: Aligns items within the field.
- `inputClass`: Custom class for the input element.
- `inputStyle`: Custom style for the input element.
- `debounce`: Debounce delay for the input.
- `maxlength`: Maximum length for the input value.
- `error`: Indicates if the field is in an error state.
- `errorMessages`: Custom error messages for the field.
- `noErrorIcon`: Hides the error icon.
- `stackLabel`: Stacks the label above the input field.
- `name`: The name attribute for the field.
- `mask`: Input mask for the field.
- `fillMask`: Fills the mask with default characters.
- `reverseFillMask`: Reverses the fill mask.
- `unmaskedValue`: Provides the unmasked value.
- `reactiveRules`: Reactive validation rules.
- `lazyRules`: Lazy validation rules.
- `loading`: Shows a loading state for the field.
- `autofocus`: Autofocuses the field on mount.
- `for`: Associates the label with the input.

### Select Field Properties

- `stackLabel`: Stacks the label above the select field.
- `options`: Array of options available in the select dropdown.
- `optionLabel`: Property name to use for displaying labels in options.
- `optionDisable`: Property name to use for disabling options.
- `hideHint`: Hides the hint text.
- `prefix`: Adds a prefix to the select field.
- `suffix`: Adds a suffix to the select field.
- `optionsDense`: Makes the options in the dropdown more compact.
- `newValueMode`: Defines how new values are added.
- `optionsDark`: Applies a dark theme to the dropdown options.
- `optionsSelectedClass`: Class applied to selected options.
- `autocomplete`: Enables autocomplete functionality.
- `bottomSlots`: Adds slots to the bottom of the dropdown.
- `hideDropdownIcon`: Hides the dropdown icon.
- `fillInput`: Fills the input with the selected value.
- `transitionShow`: Transition for showing the dropdown.
- `transitionDuration`: Duration of the transition.
- `transitionHide`: Transition for hiding the dropdown.
- `useInput`: Enables using the input as a text field.
- `behavior`: Defines the behavior of the dropdown (e.g., menu, listbox).
- `virtualScrollHorizontal`: Enables horizontal virtual scrolling.
- `multiple`: Allows multiple selections.
- `displayValue`: Custom display value for the select.
- `displayValueHtml`: Allows HTML in the display value.
- `hideSelected`: Hides the selected option from the dropdown.
- `maxValues`: Maximum number of values that can be selected.
- `menuAnchor`: Positioning anchor for the dropdown menu.
- `menuSelf`: Positioning alignment for the dropdown menu.
- `menuOffset`: Offset for the dropdown menu.
- `optionsHtml`: Allows HTML in the options.
- `optionsCover`: Covers the dropdown options.
- `menuShrink`: Shrinks the dropdown menu.
- `mapOptions`: Maps options to custom objects.
- `emitValue`: Emits the selected value instead of the object.
- `tabindex`: Tabindex for the select field.
- `tableColspan`: Colspan for the table layout.
- `errorMessage`: Custom error message for the field.
- `noErrorIcon`: Hides the error icon.

## Form Data

The `formData` prop is an object that stores the values of the form fields. It's passed as a prop to the `FormGenerator` component and can be accessed and modified as needed.

### Example

```vue
<script>
export default {
  data() {
    return {
      formData: {
        firstName: '',
        gender: '',
        address: '',
      },
      schema: {
        fields: [
          {
            type: 'text',
            label: 'First Name',
            model: 'firstName',
          },
          {
            type: 'select',
            label: 'Gender',
            model: 'gender',
            values: ['Male', 'Female'],
          },
          { label: "Male", type: "radio", model: "gender", val: "male" },
          { label: "Female", type: "radio", model: "gender", val: "female" },
        ]
      }
    }
  },
  methods: {
    submitForm() {
      console.log(this.formData);
    },
  }
}
</script>
```

## Customization

You can customize the appearance and behavior of each field using the properties defined in the schema. This allows for a highly flexible and adaptable form generation process.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.

---

Here's an additional section for the README to address future feature additions:

---

## Future Enhancements

We are continually working to improve the `FormGenerator` component and plan to add more features in future versions. These enhancements will include additional input types, more customizable properties, and advanced validation options. Our goal is to provide a comprehensive and flexible form-building solution for all your project needs.

Stay tuned for updates and new releases as we expand the capabilities of `FormGenerator`!

---

This note will inform users about ongoing development and potential improvements, encouraging them to keep an eye out for new versions.

## Users

- [Barqiat](https://barqiat.com)
- [Kitabcha](https://kitabcha.com)
- [KhanSays](https://khansays.com)
- [Schoex](https://schoex.com)

This is a basic example to get you started. Depending on your requirements, you may need to extend and customize the component further.
