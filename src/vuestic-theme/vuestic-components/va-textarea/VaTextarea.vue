<template>
  <va-input-wrapper
    class="va-textarea"
    :class="{ 'va-input-wrapper--focused': isFocused }"
    :disabled="disabled"
    :error="error"
    :success="success"
    :messages="messages"
    :error-messages="errorMessages"
  >
    <div
      class="va-textarea__slot d-flex">
      <label
        :style="labelStyles"
        aria-hidden="true"
        class="va-textarea__slot__label title"
      >
        {{ label }}
      </label>
      <textarea
        style="resize: none"
        ref="input"
        class="py-1 px-2"
        :rows="rows"
        :placeholder="placeholder"
        :disabled="disabled"
        :readonly="readonly"
        v-model="currentValue"
        @input="$emit('input', currentValue)"
        @focus="updateFocusState(true)"
        @blur="updateFocusState(false)"
      />
    </div>
    <va-icon
      @click.native="clearContent()"
      v-if="removable"
      slot="append"
      class="pointer pb-1"
      :color="error ? 'danger': ''"
      :style="{ color: '#babfc2'}"
      icon="ion ion-md-close ion"
    />
  </va-input-wrapper>
</template>

<script>
import VaInputWrapper from '../va-input/VaInputWrapper'
import VaInput from '../va-input/VaInput'

export default {
  name: 'va-textarea',
  extends: VaInput,
  components: {
    VaInputWrapper
  },
  props: {
    rows: {
      type: Number,
      default: 5
    },
    autogrow: {
      type: Boolean
    }
  },
  data () {
    return {
      currentValue: this.value,
      isFocused: false
    }
  },
  /* watch: {
    autogrow(autogrow) {
      console.log(autogrow)
      if (autogrow === true) {
        this.$nextTick(this.__adjustHeightDebounce)
      }
      else if (this.rows > 0) {
        const inp = this.$refs.input
        inp.style.height = 'auto'
      }
    }
  }, */
  computed: {
    labelStyles () {
      return {
        color: this.error ? this.$themes.danger : ''
      }
    }
  },
  methods: {
    clearContent () {
      if (this.removable) {
        this.$emit('input', '')
      }
    },
    updateFocusState (isFocused) {
      this.isFocused = isFocused
    },
    /* __adjustHeight () {

      const inp = this.$refs.input
      inp.style.height = '1px'
      inp.style.height = inp.scrollHeight + 'px'
    } */
  },
  created () {
    if (this.autogrow) {
      // this.__adjustHeightDebounce = setInterval(this.__adjustHeight, 1000)
    }
  },
}
</script>

<style lang='scss'>
  .va-textarea {

    &__slot {
      position: relative;

      &__label {
        position: absolute;
        top: -0.25rem;
        left: 0.5rem;
      }

      textarea {
        background-color: transparent;
        border-style: none;
        outline: none;
        resize: none !important;

        &::placeholder {
          color: $brand-secondary;
        }
      }
    }
  }
</style>
