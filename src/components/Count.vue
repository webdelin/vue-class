<template>
  <div class="hello">
    <h1>{{ count }}</h1>
    <button @click="clickView">clickView</button>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component
export default class Count extends Vue {
  views = 2
  @Prop() private count!: number;
  constructor() {
    super();

  }
  public clickView(){
    return this.$emit('viewchield', this.views*this.count)
  }
}
</script>