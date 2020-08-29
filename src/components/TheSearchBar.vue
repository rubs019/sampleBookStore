<template>
  <div id="searchBar">
    <b-autocomplete
      v-model="name"
      :rounded="autocomplete.rounded"
      :placeholder="autocomplete.placeholder"
      :icon="autocomplete.icon"
      :clearable="autocomplete.clearable"
      @select="option => selected = option"
    >
      <template slot="empty">
        No results found
      </template>
    </b-autocomplete>
  </div>
</template>

<script lang="ts">
import { Vue, Component } from 'vue-property-decorator'

@Component
export default class TheSearchBar extends Vue {
  autocomplete = {
    icon: 'magnify',
    placeholder: 'Search books',
    rounded: true,
    clearable: true
  }

  name = ''
  selected = null
}
</script>

<style scoped lang="scss">
#searchBar {
  width: 50%;
}
</style>
