<template>
  <VbDemo>
    <VbContainer title="Simple Textarea">
      <va-textarea
        v-model="empty"
      />
    </VbContainer>
    <VbContainer title="Textarea With Placeholder">
      <va-textarea
        v-model="empty"
        placeholder="Name"
      />
    </VbContainer>
    <VbContainer title="Textarea With Defined Rows">
      <va-textarea
        v-model="empty"
        :rows="7"
      />
    </VbContainer>
    <VbContainer title="Textarea With Label">
      <va-textarea
        v-model="text"
        label="Name"
      />
    </VbContainer>
    <VbContainer title="Textarea With Message">
      <va-textarea
        v-model="text"
        :messages="messages"/>
    </VbContainer>
    <VbContainer title="Disabled Textarea">
      <va-textarea
        v-model="text"
        disabled
      />
    </VbContainer>
    <VbContainer title="Readonly Textarea">
      <va-textarea
        v-model="text"
        readonly
      />
    </VbContainer>
    <VbContainer title="Removable Textarea">
      <va-textarea
        v-model="text"
        removable
      >
      </va-textarea>
    </VbContainer>
    <VbContainer title="Textarea With Error">
      <va-textarea
        v-model="text"
        label="Name"
        error
      />
    </VbContainer>
    <VbContainer title="Textarea With Error">
      <va-textarea
        v-model="text"
        label="Name"
        success
      />
    </VbContainer>
    <VbContainer title="Textarea With Error Message">
      <va-textarea
        v-model="text"
        label="Name"
        error
        :error-messages="errorMessages"/>
    </VbContainer>
  </VbDemo>
</template>

<script>
import VaTextarea from './VaTextarea'
import VaButton from './../va-button/VaButton'
import VaIcon from './../va-icon/VaIcon'

export default {
  components: {
    VaTextarea,
    VaButton,
    VaIcon
  },
  data () {
    return {
      empty: '',
      text: 'The Woodman set to work at once, and so sharp was his axe that the tree was soon chopped nearly through.',
      phone: '33 310-86-24',
      messages: ['Required field'],
      errorMessages: ['Detailed error message']
    }
  }
}
</script>
