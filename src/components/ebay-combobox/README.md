<h1 style="display: flex; justify-content: space-between; align-items: center;">
    <span>
        ebay-combobox
    </span>
    <span style="font-weight: normal; font-size: medium; margin-bottom: -15px;">
        DS v2.0.0
    </span>
</h1>

The `<ebay-combobox>` is a combination of a text `<input>`, and a listbox (`aria-role="listbox"`). It supports both written text by the user, as well as text selected from the listbox options.

## ebay-combobox Tag

### ebay-combobox Usage

When no selected option is specified:

```marko
<ebay-combobox name="formFieldName" autocomplete="list">
    <@option text="Option 1"/>
    <@option text="Option 2"/>
    <@option text="Option 3"/>
</ebay-combobox>
```

When a selected option is specified:

```marko
<ebay-combobox name="formFieldName" autocomplete="list" value="Option 2">
    <@option text="Option 1"/>
    <@option text="Option 2"/>
    <@option text="Option 3"/>
</ebay-combobox>
```

When the combobox should not filter the listbox options list:

```marko
<ebay-combobox name="formFieldName">
    <@option text="Option 1"/>
    <@option text="Option 2"/>
    <@option text="Option 3"/>
</ebay-combobox>
```

### ebay-combobox Attributes

| Name              | Type    | Stateful | Required | Description                                                                                                                                                                                   |
| ----------------- | ------- | -------- | -------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `name`            | String  | No       | Yes      | used for the `name` attribute of the `<input>` element                                                                                                                                        |
| `borderless`      | Boolean | No       | No       | whether the input has borders                                                                                                                                                                 |
| `disabled`        | Boolean | Yes      | No       | sets the disabled attribute of the input                                                                                                                                                      |
| `expanded`        | Boolean | Yes      | No       | sets whether the listbox is expanded                                                                                                                                                          |
| `autocomplete`    | String  | Yes      | No       | default is `none`; available values are `none` or `list`. For list, will automatically filter results while typing.                                                                           |
| `list-selection`  | String  | Yes      | No       | default is `automatic`; available values are `automatic`, `manual`. If set to automatic will automatically fill in the input with the currently highlighted item when using the up/down keys. |
| `roledescription` | String  | No       | No       | The role description for accessibility. Default text is set and will be in english. Pass this to override for different locales                                                               |
| `floating-label`  | String  | No       | No       | The label to show on the combobox which moves up when focused                                                                                                                                 |

Note: For this component, `class` is applied to the root tag, while all other HTML attributes are applied to the `input` tag.

### ebay-combobox Events

| Event                 | Data                      | Description                                                                |
| --------------------- | ------------------------- | -------------------------------------------------------------------------- |
| `collapse`            |                           | collapsed content                                                          |
| `expand`              |                           | expanded content                                                           |
| `change`              | `{ el, index, selected }` | same as the `onChange` event, which fires on blur                          |
| `input-change`        | `{ el, index, selected }` | same as the `onInput` event, which fires with every keypress               |
| `select`              | `{ el, index, selected }` | similar to a `<select>`, which fires when an option is clicked or selected |
| `floating-label-init` | `{ el, index, selected }` | when floating label finishes initializing                                  |

## @option Tag

### @option Usage

```marko
<@option text="Option 1"/>
```

### @option Attributes

| Name     | Type    | Stateful | Required | Description                                                                  |
| -------- | ------- | -------- | -------- | ---------------------------------------------------------------------------- |
| `text`   | String  | No       | No       | string to use in the option                                                  |
| `sticky` | Boolean | No       | No       | If true, the option will always be shown even if it doesn't match the filter |
