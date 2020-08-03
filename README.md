# vue-naira-input

A Vue component for inputting Naira-formatted amounts.

## Installation

```js
npm i -S vue-naira-input
```

### Browser

```html
<script type="text/javascript" src="https://unpkg.com/vue"></script>
<script type="text/javascript" src="https://unpkg.com/vue-naira-input"></script>
<script type="text/javascript">
  Vue.use(NairaInput);
</script>
```

### Module

```js
import NairaInput from 'vue-naira-input';
```

## Usage

Once installed, it can be used in a template as simply as:

```html
<naira-input ref="nairaInput" :initial-amount="initialAmount" v-model="amount" />
```

Or styled as a Bootstrap input:

```html
<naira-input class="form-control" ref="nairaInput" :initial-amount="initialAmount" v-model="amount" />
```

The currency prefix can be changed:

```html
<naira-input ref="nairaInput" currency-symbol="$" :initial-amount="initialAmount" v-model="amount" />
```

To clear the input, call:
```js
this.$refs.nairaInput.clear();
```

To reset the input to the initial value, call:
```js
this.$refs.nairaInput.reset();
```
