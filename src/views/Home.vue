<template>
  <div>
    <div>
      <button @click="createEntryPoint">Create New Entrypoint</button>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';

@Component({
  components: {
  },
})
export default class Home extends Vue {
  private createEntryPoint() {
    this.$router.push('/createEntryPoint');
  }
}
</script>
