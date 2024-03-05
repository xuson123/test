
<template>
  <el-table :data="data" style="width:100%">
    <el-table-column
    prop="username"
    label="用户名"></el-table-column>
    <el-table-column
    prop="email"
    label="邮箱"></el-table-column>
    <el-table-column
    prop="registrationDate"
    label="注册日期"
    column-key="registrationDate"
    :filters="[{text:'2022-01-01T00:00:00Z',value:'2022-01-01T00:00:00Z'}]"
    :filters-method="filterHandler"></el-table-column>
    <el-table-column label="操作">
            <el-button size="mini" @click="handleEdit">编辑</el-button>
            <el-button size="mini" @click="use">启用/禁用</el-button>
            <el-button size="mini" @click="delet">删除</el-button>
    </el-table-column>
  </el-table>
</template>

<script>
export default {
  name: "",
  data() {
    return {
      status: "success",
      data: [
        {
          _id: "61f7c9e68d2fa1b8d4a2a9f0",
          username: "john.doe",
          email: "john.doe@example.com",
          registrationDate: "2022-01-01T00:00:00Z",
          status: { code: 1, description: "Active" },
        },
        {
          _id: "61f7c9e68d2fa1b8d4a2a9f0",
          username: "john.doe",
          email: "john.doe@example.com",
          registrationDate: "2022-01-02T00:00:00Z",
          status: { code: 1, description: "Active" },
        },
        // 更多用户...
      ],
    };
  },

  components: {},
  methods:{
    filterHandler(value,row,column){
        const property = column['property'];
        return row[property] === value;
    },
    Changetime(dateString) {
      let date = new Date(dateString);
      let year = date.getFullYear();
      let month = date.getMonth() + 1;
      let day = date.getDate();
      let hours = date.getHours();
      let minutes = date.getMinutes();
      let seconds = date.getSeconds();
      return `${year}-${month}-${day} ${hours}:${minutes}:${seconds}`;
    },
    countAver() {
      for (let i = 0; i < this.data.length; i++) {
        // let arr = this.data
        // arr[i].registrationDate = this.
        this.data[i].registrationDate = this.Changetime(this.data[i].registrationDate)
        // this.tableData[i].createdAt = this.time(this.tableData[i].createdAt);
      }
    },
    handleEdit(){

    },
    use(){

    },
    delet(){
        alert('确认删除吗')
    },
  },
  mounted(){
    this.countAver()
  }
};
</script>
<style scoped>
</style>
