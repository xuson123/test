
<template>
  <div>
    <ChildComponent :tableData="tableData" :updata="updata"/>
  </div>
  
</template>

<script>
import ChildComponent from './ChildComponent.vue';
export default {
  name: "",
  data() {
    return {
      status: "success",

      tableData: [
        {
          groupId: 1,
          groupName: "Admin Group",
          users: [
            {
              id: 1,
              name: "John Doe",
              email: "john.doe@example.com",
              role: "admin",
              createdAt: "2023-01-01T00:00:00Z",
            },
            // 更多用户...
          ],
        },
        {
          groupId: 2,
          groupName: "Editor Group",
          users: [
            // ...
          ],
        },
        // 更多用户组...
      ],
    };
  },
  components: {ChildComponent},
  methods:{
    updata(){
      console.log('@@@,111')
    }
  }
};
</script>
<style scoped>
</style>
