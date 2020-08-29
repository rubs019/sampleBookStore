<template>
  <b-navbar>
    <template slot="brand">
      <b-navbar-item tag="router-link" :to="{ path: '/' }">
        <img
          src="https://raw.githubusercontent.com/buefy/buefy/dev/static/img/buefy-logo.png"
          alt="Lightweight UI components for Vue.js based on Bulma"
        >
      </b-navbar-item>
    </template>
    <template slot="start">
      <TheSearchBar />
    </template>

    <template slot="end">
      <b-navbar-item tag="div">
        <div class="buttons">
          <CartButton />
          <a class="button is-primary">
            <strong>Sign up</strong>
          </a>
          <a class="button is-light">
            Log in
          </a>
        </div>
      </b-navbar-item>
    </template>
  </b-navbar>
</template>

<script lang="ts">
import { Vue, Component } from 'vue-property-decorator'
import CartButton from '@/components/button/CartButton.vue'
import TheSearchBar from '@/components/TheSearchBar.vue'

@Component({
  components: { CartButton, TheSearchBar }
})
export default class TheNavbar extends Vue {
}
</script>

<style lang="scss">
.navbar-start {
  width: 100%;
  justify-content: center;
  align-items: center;
}

.navbar-expanded {
  width: 100%
}

</style>
