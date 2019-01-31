<template>
  <VbDemo>
    <VbContainer>
      <table class="table table-bordered">
        <tr>
          <th>Description</th>
          <th>Vuestic Button</th>
        </tr>
        <tr>
          <td>Types</td>
          <td>
            <va-dropdown-button :items="items" position="left">
              Default Button
            </va-dropdown-button>
          </td>
        </tr>
      </table>
    </VbContainer>
  </VbDemo>
</template>

<script>
export default {
  data () {
    return {
      items: [ 'One', 'Two', 'Three' ]
    }
  },
}
</script>
