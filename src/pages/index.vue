<template>
  <div class="content">
    <TheNavbar />
  </div>
</template>

<script lang="ts">
import { Vue, Component } from 'vue-property-decorator'
import TheNavbar from '@/components/TheNavbar.vue'

@Component({
  components: { TheNavbar }
})
export default class IndexPage extends Vue {
}
</script>

<style scoped lang="scss">

</style>
