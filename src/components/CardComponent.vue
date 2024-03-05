
<template>
<div>
  <div v-for="a in tableData" :key="a.id">
        <ul>
            <li v-for="b in a.users" :key="b.id">姓名：{{ b.name }} 邮箱：{{ b.email }}  角色：{{ b.role }}</li>
            <button @click="up">更新</button>
        </ul>
        
    </div>
</div>
</template>

<script>
export default {
  name: '',
  components: {},
  props:['tableData','updata:{type: Function,default: null}'],
  methods:{
    up(){
        this.updata()
    }
  }
}
</script>
<style scoped>

</style>
