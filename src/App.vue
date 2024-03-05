<template>
  <div class="app">
    <!-- <Product/> -->
    <!-- <Test2/> -->
    <!-- <ParentComponent/> -->
    <UserManagementComponent/>
  </div>
</template>

<script>
import Product from './components/Product.vue';
import Test2 from '@/components/Test2.vue'
import ParentComponent from './components/ParentComponent.vue';
import ChildComponent from './components/ChildComponent.vue';
import UserManagementComponent from './components/UserManagementComponent.vue';
export default {
  name: 'App',
  data(){
    return{
      
  }
  },
  components:{
    Product,Test2,ParentComponent,ChildComponent,UserManagementComponent
  }

}
</script>

<style>


</style>
