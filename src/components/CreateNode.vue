<template>
  <div>
    <div>
      Name: <input type="text" v-model="name">
      Description: <input type="text" v-model="desc">
    </div>
    <div>
      Repo: <input type="text" v-model="repo">
      Path: <input type="text" v-model="path">
    </div>
    <div>
      <button @click="loadFile">Load</button>
    </div>
    <div>
      <pre>{{ result }}</pre>
    </div>
    <div>

    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
// import * as env from 'dotenv';

@Component({
  components: {
  },
})
export default class CreateNode extends Vue {
  private name: string = '';
  private desc: string = '';
  private repo: string = '';
  private path: string = '';

  private result: any = '';

  private async loadFile() {
    const res = await fetch(`https://api.github.com/repos/Holayn/${this.repo}/contents/${this.path}`, {
      headers: {
        accept: 'application/vnd.github.VERSION.raw',
      },
    });
    this.result = await res.text();
  }
}
</script>
