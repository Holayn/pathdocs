<template>
  <div>
    <div>
      <h3>Entrypoint Name</h3>
      Name: <input type="text" v-model="name">
      Description: <input type="text" v-model="desc">
    </div>
    <hr>
    <div>
      <h3>Create Node</h3>
      <CreateNode></CreateNode>
    </div>
    
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import CreateNode from '../components/CreateNode.vue';

@Component({
  components: {
    CreateNode,
  },
})
export default class Home extends Vue {
  private name: string = '';
  private desc: string = '';
}
</script>
