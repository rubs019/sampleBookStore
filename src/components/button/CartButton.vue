<template>
  <a class="button is-success">
    <b-icon
      icon="cart"
      size="is-small"
    />
    Cart
    <b-tag id="nb_item" rounded>{{ nbItem }}</b-tag>
  </a>
</template>

<script lang="ts">
import { Vue, Component } from 'vue-property-decorator'

@Component
export default class CartButton extends Vue {
  nbItem = 2
}
</script>

<style scoped lang="scss">
  #nb_item {
    margin-left: 5px;
  }
</style>
