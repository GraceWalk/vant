# Switch

### Install

Register component globally via `app.use`, refer to [Component Registration](#/en-US/advanced-usage#zu-jian-zhu-ce) for more registration ways。

```js
import { createApp } from 'vue';
import { Switch } from 'vant';

const app = createApp();
app.use(Switch);
```

## Usage

### Basic Usage

```html
<van-switch v-model="checked" />
```

```js
import { ref } from 'vue';

export default {
  setup() {
    const checked = ref(true);
    return { checked };
  },
};
```

### Disabled

```html
<van-switch v-model="checked" disabled />
```

### Loading

```html
<van-switch v-model="checked" loading />
```

### Custom Size

```html
<van-switch v-model="checked" size="24px" />
```

### Custom Color

```html
<van-switch v-model="checked" active-color="#ee0a24" inactive-color="#dcdee0" />
```

### Async Control

```html
<van-switch :model-value="checked" @update:model-value="onUpdateValue" />
```

```js
import { ref } from 'vue';
import { Dialog } from 'vant';

export default {
  setup() {
    const checked = ref(true);
    const onUpdateValue = (newValue) => {
      Dialog.confirm({
        title: 'Confirm',
        message: 'Are you sure to toggle switch?',
      }).then(() => {
        checked.value = newValue;
      });
    };

    return {
      checked,
      onUpdateValue,
    };
  },
};
```

### Inside a Cell

```html
<van-cell center title="Title">
  <template #right-icon>
    <van-switch v-model="checked" size="24" />
  </template>
</van-cell>
```

## API

### Props

| Attribute | Description | Type | Default |
| --- | --- | --- | --- |
| v-model | Check status of Switch | _ActiveValue \| InactiveValue_ | `false` |
| loading | Whether to show loading icon | _boolean_ | `false` |
| disabled | Whether to disable switch | _boolean_ | `false` |
| size | Size of switch | _number \| string_ | `30px` |
| active-color | Background color when active | _string_ | `#1989fa` |
| inactive-color | Background color when inactive | _string_ | `white` |
| active-value | Value when active | _any_ | `true` |
| inactive-value | Value when inactive | _any_ | `false` |

### Events

| Event  | Description                       | Parameters          |
| ------ | --------------------------------- | ------------------- |
| change | Emitted when check status changed | _value: any_        |
| click  | Emitted when component is clicked | _event: MouseEvent_ |

### Less Variables

How to use: [Custom Theme](#/en-US/theme).

| Name | Default Value | Description |
| --- | --- | --- |
| @switch-size | `30px` | - |
| @switch-width | `2em` | - |
| @switch-height | `1em` | - |
| @switch-node-size | `1em` | - |
| @switch-node-background-color | `@white` | - |
| @switch-node-box-shadow | `0 3px 1px 0 rgba(0, 0, 0, 0.05)` | - |
| @switch-background-color | `@white` | - |
| @switch-on-background-color | `@blue` | - |
| @switch-transition-duration | `@animation-duration-base` | - |
| @switch-disabled-opacity | `@disabled-opacity` | - |
| @switch-border | `@border-width-base solid rgba(0, 0, 0, 0.1)` | - |
