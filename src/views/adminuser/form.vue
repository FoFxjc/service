<template>
  <div class="app-container">
    <el-form ref="form" :model="form" label-width="120px">
      <el-form-item label="User name" style="width: 50%">
        <el-input v-model="form.name" />
      </el-form-item>
      <el-form-item label="Gender">
        <el-select v-model="form.region">
          <el-option label="Zone one" value="Male" />
          <el-option label="Zone two" value="Female" />
        </el-select>
      </el-form-item>
      <el-form-item label="Nick name" style="width: 50%">
        <el-input v-model="form.name" />
      </el-form-item>
      <el-form-item label="Email" style="width: 50%">
        <el-input v-model="form.name" />
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
        name: "",
        region: "",
        date1: "",
        date2: "",
        delivery: false,
        type: [],
        resource: "",
        desc: "",
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
