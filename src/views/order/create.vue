<template>
  <div class="app-container">
    <el-form ref="form" :model="form" label-width="120px">
      <el-form-item label="任务名称">
        <el-input v-model="form.task" />
      </el-form-item>
      <el-form-item label="任务发布者">
        <el-input v-model="form.submitter" />
      </el-form-item>
      <el-form-item label="任务状态">
        <el-input v-model="form.status" />
      </el-form-item>
      <el-form-item label="时间">
        <el-select v-model="form.region" placeholder="please select your zone">
          <el-option label="Zone one" value="shanghai" />
          <el-option label="Zone two" value="beijing" />
        </el-select>
      </el-form-item>
      <el-form-item>
        <el-button type="primary" @click="onSubmit">Create</el-button>
        <el-button @click="onCancel">Cancel</el-button>
      </el-form-item>
    </el-form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      form: {
        submitter: "qyvxelkfge",
        task: "nulla",
        status: "sunt Lorem eu",
        time: "1970-11-20 09:32:15",
        owner: "psowvalsbd",
      },
    };
  },
  methods: {
    onSubmit() {
      this.$message("submit!");
    },
    onCancel() {
      this.$message({
        message: "cancel!",
        type: "warning",
      });
    },
  },
};
</script>

<style scoped>
.line {
  text-align: center;
}
</style>
