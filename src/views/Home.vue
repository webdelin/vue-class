<template>
  <div>
    <Count :count="count" @viewchield="viewsClick"/>
    <button @click="abb">ABB</button>
    <button @click="add">ADD</button>
    <h2>Views {{views}}</h2>
  </div>
</template>

<script lang="ts">
import {Component, Prop, Vue} from 'vue-property-decorator';
import Count from '@/components/Count.vue'; // @ is an alias to /src

@Component({
  components: {
    Count,
  },
})
export default class Home extends Vue {
  count = 1
  views = 0
  private add(){
    return this.count++
  }
  private abb(){
    return this.count--
  }

  public viewsClick(data: number){
    console.log('EVENT ', data)
    return this.views = data
  }
}
</script>
