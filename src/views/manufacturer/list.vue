<template>
  <div class="app-container">
    <el-table
      v-loading="listLoading"
      :data="manuList"
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
      <el-table-column label="制造商名称" width="200" align="center">
        <template slot-scope="scope">
          {{ scope.row.ResName }}
        </template>
      </el-table-column>
      <el-table-column label="加工能力">
        <template slot-scope="scope">
          <span>{{ scope.row.Res }}</span>
        </template>
      </el-table-column>
      <!-- <el-table-column
        class-name="status-col"
        label="订单状态"
        width="200"
        align="center"
      >
        <template slot-scope="scope">
          <el-tag :type="scope.row.status | statusFilter">{{
            scope.row.status
          }}</el-tag>
        </template>
      </el-table-column> -->
      <!-- <el-table-column
        align="center"
        prop="created_at"
        label="Display_time"
        width="200"
      >
        <template slot-scope="scope">
          <i class="el-icon-time" />
          <span>{{ scope.row.display_time }}</span>
        </template>
      </el-table-column> -->
    </el-table>
  </div>
</template>

<script>
import { getList } from "@/api/table";

export default {
  filters: {
    statusFilter(status) {
      const statusMap = {
        published: "success",
        draft: "gray",
        deleted: "danger",
      };
      return statusMap[status];
    },
  },
  data() {
    return {
      list: null,
      listLoading: true,
      orderList: [
        {
          submitter: "qyvxelkfge",
          task: "nulla",
          status: "sunt Lorem eu",
          time: "1970-11-20 09:32:15",
          owner: "psowvalsbd",
        },
        {
          submitter: "wuqq",
          task: "esse",
          status: "exercitation quis",
          time: "1976-08-28 08:00:38",
          owner: "jwsdp",
        },
      ],
      manuList: [
        {
          ResName: "Helen Perez",
          Res: ["occaecat dolore"],
        },
        {
          ResName: "Barbara Hall",
          Res: [
            "consectetur consequat reprehenderit",
            "est ex reprehenderit et consequat",
            "cillum cupidatat et in esse",
          ],
        },
      ],
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
