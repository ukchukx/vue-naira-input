<template>
  <!-- eslint-disable -->
  <masked-input type="text" v-model="amount" :mask="nairaMask" :guide="false" />
</template>
<script>
import MaskedInput from 'vue-text-mask';
import createNumberMask from 'text-mask-addons/dist/createNumberMask';

export default {
  name: 'NairaInput',
  components: {
    MaskedInput
  },
  props: {
    initialAmount: {
      type: Number,
      default: () => 0
    }
  },
  data() {

    return {
      nairaMask: createNumberMask({ prefix: '₦', allowDecimal: true }),
      amount: `${this.initialAmount}`
    };
  },
  watch: {
    amount(str) {
      const amount = str.length ? parseFloat(str.replace(/[₦,]/g, '')) : 0;
      this.$emit('input', amount);
    }
  },
  methods: {
    clear() {
      this.amount = '';
    }
  }
};
</script>

