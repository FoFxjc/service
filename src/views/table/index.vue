<template>
  <div class="app-container">
    <el-card class="box-card"> Account List </el-card>
    <el-table
      v-loading="listLoading"
      :data="list"
      element-loading-text="Loading"
      border
      fit
      highlight-current-row
    >
      <el-table-column align="center" label="ID" width="95">
        <template slot-scope="scope">
          {{ scope.$index }}
        </template>
      </el-table-column>
      <el-table-column label="Name" align="center">
        <template slot-scope="scope">
          {{ scope.row.name }}
        </template>
      </el-table-column>
      <el-table-column label="Nickname" align="center">
        <template slot-scope="scope">
          <span>{{ scope.row.nickname }}</span>
        </template>
      </el-table-column>
      <el-table-column label="Email" align="center">
        <template slot-scope="scope">
          {{ scope.row.email }}
        </template>
      </el-table-column>
      <el-table-column
        class-name="status-col"
        label="Payment"
        width="110"
        align="center"
      >
        <template slot-scope="scope">
          <el-tag :type="scope.row.payment | statusFilter">{{
            scope.row.payment
          }}</el-tag>
        </template>
      </el-table-column>
      <el-table-column
        align="center"
        prop="created_at"
        label="Register"
        width="200"
      >
        <template slot-scope="scope">
          <i class="el-icon-time" />
          <span>{{ scope.row.register_time }}</span>
        </template>
      </el-table-column>
      <el-table-column label="Action" width="300" align="center">
        <template slot-scope="scope">
          <el-button @click="handleClick(scope.row)" size="mini" type="info"
            >Detail</el-button
          >
          <el-button size="mini" type="danger">Delete</el-button>
          <el-button size="mini" type="warning">Reset Password</el-button>
        </template>
      </el-table-column>
    </el-table>
  </div>
</template>

<script>
import { getList } from "@/api/table";

export default {
  filters: {
    statusFilter(status) {
      const statusMap = {
        Visa: "success",
        MasterCard: "gray",
        JCB: "danger",
      };
      return statusMap[status];
    },
  },
  data() {
    return {
      list: null,
      listLoading: true,
    };
  },
  created() {
    this.fetchData();
  },
  methods: {
    fetchData() {
      this.listLoading = true;
      getList().then((response) => {
        this.list = response.data.items;
        this.listLoading = false;
      });
    },
  },
};
</script>
<style lang="postcss">
.box-card {
  margin-bottom: 20px;
  font-size: 20px;
  font-weight: bold;
}
</style>
