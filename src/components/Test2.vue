
<template>
  <el-table
    :data="tableData"
    style="width: 100%"
    :default-sort="{ prop: 'date', order: 'descending' }"
  >
    <el-table-column prop="groupId" label="用户分组" sortable width="1000">
      <template slot-scope="scope">
        <el-table :data="scope.row.users" style="width: 100%">
          <el-table-column
            prop="name"
            label="用户名"
            :filters="[{ text: 'John', value: 'John' }]"
            :filter-method="filterMetho"
          >
          </el-table-column>
          <el-table-column
            prop="email"
            label="邮箱"
            :filters="[{ text: 'example', value: 'example' }]"
            :filter-method="filterMetho"
          >
          </el-table-column>
          <el-table-column
            prop="role"
            label="角色"
            :filters="[{ text: 'admin', value: 'admin' }]"
            :filter-method="filterMetho"
          >
          </el-table-column>
          <el-table-column
            prop="createdAt"
            label="创建时间"
            :filters="[{ text: '01-01', value: '01-01' }]"
            :filter-method="filterMetho"
          >
          </el-table-column>
        </el-table>
      </template>
    </el-table-column>
    <el-table-column prop="groupName" label="分组名称" width="150">
    </el-table-column>
  </el-table>
</template>

<script>
export default {
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
              d: "",
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
  components: {},
  methods: {
    filterMethod(value, row) {
      return row.name === value;
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
      for (let i = 0; i < this.tableData.length; i++) {
        let arr = this.tableData[i].users
        for(let j=0;j < arr.length;j++){
          arr[j].createdAt = this.Changetime(arr[j].createdAt)
        }
        // this.tableData[i].createdAt = this.time(this.tableData[i].createdAt);
      }
    },
  },
  mounted() {
    this.countAver();
  },
};
</script>
<style scoped>
</style>
