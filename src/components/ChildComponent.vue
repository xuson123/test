
<template>
<div class="app">
  <CardComponent :tableData="tableData" :updata="updata"/>
</div>
</template>

<script>
import CardComponent from './CardComponent.vue';
export default {
  name: 'ChildComponent',
  components:{CardComponent},
  data(){
    
  },
  props:['tableData','updata'],
  methods:{
   
  }
}
</script>
<style scoped>

</style>
