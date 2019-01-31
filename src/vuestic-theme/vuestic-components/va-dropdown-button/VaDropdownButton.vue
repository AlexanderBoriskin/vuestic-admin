<template>
  <div>
    <va-button
      :outline="outline"
      :flat="flat"
      :color="color"
      :small="small"
      :large="large"
      :disabled="disabled"
      :icon="icon"
      class="theme-toggle"
      icon-right="ion-ios-arrow-down arrow-down">
      <slot/>
      <vuestic-dropdown
        v-model="value"
        :position="position"
      >
        <div class="q-popover__container">
          <a
            class="dropdown-item"
            href="#"
            v-for="(item, index) in items"
            :key="index"
          >
            {{ item }}
          </a>
          <div class="flex lg6"></div>
        </div>
      </vuestic-dropdown>
    </va-button>
  </div>
</template>

<script>
export default {
  name: 'va-dropdown-button',
  props: {
    items: {
      type: Array,
    },
    value: {
      type: [ String, Object ],
    },
    split: {
      type: Boolean
    },
    outline: {
      type: Boolean
    },
    flat: {
      type: Boolean
    },
    color: {
      type: String
    },
    small: {
      type: Boolean
    },
    large: {
      type: Boolean
    },
    disabled: {
      type: Boolean
    },
    icon: {
      type: String
    },
    position: {
      type: String,
      validator: function (value) {
        return ['top', 'right', 'bottom', 'left'].includes(value)
      }
    },
  },
  computed: {
    buttonClass () {
      return {
        'va-button--success': this.color === 'success',
        'va-button--info': this.color === 'info',
        'va-button--danger': this.color === 'danger',
        'va-button--warning': this.color === 'warning',
      }
    },
    hasTitleData () {
      return this.$slots.default
    },
    inputListeners () {
      const vm = this
      return Object.assign({},
        this.$listeners,
        {
          click: function (event) {
            vm.$emit('click', event)
          }
        }
      )
    }
  },
}
</script>

<style lang='scss'>
 .dropdown-item {
   color: #4ae387;
 }
</style>
